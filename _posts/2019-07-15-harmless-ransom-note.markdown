---
title: "Harmless Ransom Note"
layout: post
date: 2019-07-15 19:58
image:
headerImage: false
tag:
- Algorithms
- Data Structures
- Javascript
- Hash Tables
star: true
category: blog
author: woodylucas
description: How to use a hash table.
---
Oh my oh my…. Algorithms WHY WHY WHY!!!!!!

![Alt Text](https://media.giphy.com/media/KupdfnqWwV7J6/giphy.gif){:height="50%" width="200%"}

Embarking on my life as a Software Engineer. Applying for jobs, you are faced with the challenge to take on algorithms. Which has been an epic failure on my end. Don’t feel sorry for me it’s just apart of the process. The fear of algorithms kills me, but what better way to conquer any fear, then attacking those issue head on. *Friendly Reminder* Algos are just basically a way for companies to test your problem solving skills as a programmer. Remember don’t let algorithms rule you, you rule algorithms. On my road to finding my first programming job I will be writing a blog on every algorithm I have faced, and conquered. The reason I am doing this is to improve my comprehension level, with an approach of teaching what I have learned. The Feynman Technique, which I will discuss more about in my upcoming blog “A Programmers Path, Avoid Tutorial Purgatory.” Hey that has a nice ring to it.(Let’s just say I made that name on the spot) But I digress. Back to the problem at hand.

The harmless ransom note-basically you are given two strings. You have to find whether you can make up the first string with words present in the second string. For our non programmers, let’s say you have a magazine and you want to create a note text with every word that is present in this specific magazine text, but you’re only allowed to use the words you have been given.
Now, lets’ attack this algorithm coding challenge.

When we first start we should create a function that takes two arguments.

```javascript

function harmlessRansomNote(noteText, magazineText) {
}


```

The first step is to make a collection of the words we have in our strings. The reason being is that we want to have access to every specific word so we can create our note. *Sidenote* When I say collection majority of the time it is an array. An array can be known as a collection, or list. Whenever you see those words, it means ARRAY.

![Alt Text](https://media.giphy.com/media/eBpiVHAzU8XXtvPCae/giphy.gif){:height="50%" width="200%"}


```javascript


function harmlessRansomNote(noteText, magazineText {
  const notesArr = noteText.split(' '); // creates an array.
  const magazineArr = magazineText.split(' ');
}

```


I created an array from our strings with JavaScript’s split method.
With our string being an array of every specific word, we can now iterate through every item(word) in the array.
But wait, before we go any further we need to address something. The whole point of this code challenge is to compare two strings with each other. So how can we do that? Hey, I thought you will never ask. We have arrays of every specific word in our strings, but we need to be able to keep track of them. This is where we implement an algorithm. I will be using a hash table. I will use this object to keep track of every word, and how many times it has been used.

```javascript

function harmlessRansomNote(noteText, magazineText {
  const notesArr = noteText.split(' ')// creates an array.
  const magazineArr = magazineText.split(' ')
  const magazineObj = {}
}

```

The goal of this is to have every word that is present be presented like this {this: 1}. This will just show how many times this word is present in that array of words. Back to coding…

```javascript
 const magazineObj = {}; // hash table. The goal is to keep track of every specific word. Should look like this { this: 1 }

 magazineArr.forEach(word => {
   if(!magazineObj[word]){ // if the word isn't present, then set magazineObj equal to zero. The reason being we're stating it doesn't exist.
     magazineObj[word] = 0;
   }
   magazineObj[word]++;
   // then add the word to the hash table.
 });
```

We iterate through the magazine array, to see if the word exist. See how we are using the variable magazineObj (which is our hash table). To keep track of every string placed in that array. So if the word isn’t present in the magazineObj, then set magazineObj = 0. This is just saying the word is not present, so when we add a word it will start at zero, and we will increment up. So now if we place a new word in the string it will count how many times its present.

```javascript

let noteIsPossible = true;

  notesArr.forEach( word => {
    if(magazineObj[word]) { // if the word is present in the object, we are going to remove that word to avoid duplicates.
      magazineObj[word]--;
      if (magazineObj[word] < 0)  { // less than zero, then set noteIsPossible to false because it doesn't exist.
        noteIsPossible = false;
      }

    } else {
      noteIsPossible = false; // if we don't have all the necessary words possbile. We will mark it false.
    }
  })
  return noteIsPossible;
}


```

See now we are iterating, through the note’s array, to basically to check if the word is present in the magazineObj. I declared a boolean variable first, so I can check if the words are present in both arrays. If the words are present, we will remove (decrement) that specific word from the magazineObj. Reason being is to avoid any duplicates. I also created an, additional if statement. This condition checks to see if the word isn’t present, then it doesn’t exist so we return false.


So if you really don’t understand why I used magazineObj[word ] < 0. The logic behind this is that we are using arrays, and the indices for arrays start at 0. So if the word in the array is at index -1, that means it isn’t present. Which gives us the ability to create a condition that basically checks if the index of that word is 0 or above, we have a word, if it is less than 0, there’s no word.
Solution:

```javascript

function harmlessRansomNote(note, magazine) {
  const notesArr = note.split(' '); // creates an array.
  const magazineArr = magazine.split(' ');
  const magazineObj = {}; // hash table. The goal is to keep track of every specific word. Should look like this { this: 1 }

  magazineArr.forEach(word => {
    if(!magazineObj[word]){ // if the word isn't present, then set magazineObj equal to zero. The reason being we're stating it doesn't exist.
      magazineObj[word] = 0;
    }
    magazineObj[word]++;
    // then add the word to the hash table.
  });

  let noteIsPossible = true;

  notesArr.forEach( word => {
    if(magazineObj[word]) { // if the word is present in the object, we are going to remove that word to avoid duplicates.
      magazineObj[word]--;
      if (magazineObj[word] < 0)  { // less than zero, then set noteIsPossible to false because it doesn't exist.
        noteIsPossible = false;
      }

    } else {
      noteIsPossible = false; // if we don't have all the necessary words possbile. We will mark it false.
    }
  })
  return noteIsPossible;
}

harmlessRansomNote('this is a secret note for you from a secret admirer', 'puerto rico is a place of great wonder and excitement it has many secret waterfall locations that i am an admirer of you must hike quite a distance to find the secret places as they are far from populated areas but it is worth the effort a tip i have for you is to go early in the morning when it is not so hot out also note that you must wear hiking boots this is one of the best places i have ever visited');
```
