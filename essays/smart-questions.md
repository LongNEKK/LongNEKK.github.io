---
layout: essay
type: essay
title: "Musings Upon The Death of Forum Questions"
# All dates must be YYYY-MM-DD format!
date: 2025-01-28
published: true
labels:
  - Questions
  - Answers
  - StackOverflow
---

<img width="300px" class="rounded float-start pe-4" src="../img/labyrinth.png">

## The Obscurity and Ethics of Raising The Dead
A relentless search for knowledge has propelled your mind forward - sweat beads upon your brow and a quiet, aching fatigue has crept into your spirit. For all of your hours of discovery and investigation, one thing haunts you still and one question yet remains to trail after you. Scrolling through the Internet, you have been scanning your eyes across the epochs, and the familiar becomes unfamiliar as you begin to realize, "Maybe nobody ever has experienced my trials...". Defeated, you find yourself wondering what led you to this moment - a pioneer, a voyager into the unknown, and perhaps even a warning to all that come after. Sluggishly clicking and highlighting, you feel that you are not yet ready for the task at hand.  Unexpectedly, something shines in the periphery of your browser tab - a blue, unopened link. Your pulse quickens as you read the issue - it sounds just like yours! The room brightens, and you find yourself singing the praises of this worthy hero before you. However, the heart shatters as you read the date... posted 8 years ago! Scrolling down, the pits of despair seem ever deeper as you note the only reply - they asked for clarification on the problem. The blue, unopened link had now become the blue of the sea, and you were planted upon a voyage that led to nowhere. The land upon the horizon had been a trick of the eye, and quickly but surely, the storm clouds were rolling in. If only the captain of this ship had asked a smarter question! Looking upon the captain's corpse in this hopeless vessel, a decision is before you. Shall I take the reins of fortune myself, and steer a forum discussion towards the safety of land, or will I commit the grave sin of necro-posting - raising the post (and the captain) from the dead by posting to this ancient thread? As you resolve yourself to this newfound position, it may be best to equip yourself with the tools necessary to ask smart questions.



## Well-Thought Questions 

The daunting task of steering this vessel requires the proper management of its numerous posts. As a result, it is always to best to consult an example and rely on the wisdom of the past. Many of the possible considerations of how one might ask and format questions include providing as much detail as possible, listing relevant specifications to the given question, and making the question as close-ended as can be managed. One such site where a programmer might ask smart questions includes StackOverflow - a site where posters may provide questions and answers to. The culture of the site strictly abides to a set of rules and customs in order to provide thoughtful answers to well-considered questions. Due to this culture, it can be a great place to find questions of a high caliber. 

In the [upcoming example](https://stackoverflow.com/questions/208105/how-do-i-remove-a-property-from-a-javascript-object), the user asks a relevant, specific, and close-ended question on the site to assist others in providing effective and concise answers to their issue. The thread poster is determining how to remove an object's property from an object in JavaScript - there are further details of this question show below. 

```
Q: How do I remove a property from a JavaScript object?
Given an object:

let myObject = {
  "ircEvent": "PRIVMSG",
  "method": "newURI",
  "regex": "^http://.*"
};
How do I remove the property regex to end up with the following myObject?

let myObject = {
  "ircEvent": "PRIVMSG",
  "method": "newURI"
};
```

In the above example, the heading of the question is short and meaningful which provides instantaneous clarity as well room for an answer to include additional information. In addition, the question continues by giving an example of an object both before and after the deletion of a property. This provides strict boundaries to the question that cuts any confusion from the matter regarding what is meant by "deletion". As a result, this question is an excellent example of asking a question in an intelligent and effective manner. Provided below, I have also included a sample answer from among the many included in the thread. 

```
A: To remove a property from an object (mutating the object), you can do it by using the delete keyword, like this:

delete myObject.regex;
// or,
delete myObject['regex'];
// or,
var prop = "regex";
delete myObject[prop];


var myObject = {
  "ircEvent": "PRIVMSG",
  "method": "newURI",
  "regex": "^http://.*"
};
delete myObject.regex;

console.log(myObject);

For anyone interested in reading more about it, Stack Overflow user kangax has written an incredibly in-depth blog post about the delete statement on their blog, Understanding delete. It is highly recommended.

If you'd like a new object with all the keys of the original except some, you could use destructuring.

let myObject = {
  "ircEvent": "PRIVMSG",
  "method": "newURI",
  "regex": "^http://.*"
};

// assign the key regex to the variable _ indicating it will be unused
const { regex: _, ...newObj } = myObject;

console.log(newObj);   // has no 'regex' key
console.log(myObject); // remains unchanged
```
 
There were 40 answer to this question in total, but this answer was by far the most popular. Of course, the reason is clear. They relay the answer in the very first sentence followed by multiple demos and examples. Then, they reference another user's post about the delete keyword if any reader is interested in further information. A referral to another poster is an excellent exercise in courtesy and humility which adds to their own credibility as a reliable source. Finally, an alternative using destructuring was provided in case the poster was curious about the potential alternatives to what they were doing. As a result, this thread was highly viewed and upvoted due to the high quality of questions and answers contained within. 

## The Death of A Question 

A question such as the one [below](https://steamcommunity.com/app/377160/discussions/0/4512128114436476359/). is not an effective question that warrants a thoughtful response whatsoever. In contrast, it invites derision and hostility towards the poster when it might not be otherwise deserved.

```
Q: Fallout London: f*ck this
So I did the downgrader, opened in GOG, plugged in the path and now it tells me "Current game build is not supported. Please install version 1.10.163.0 of the Fallout 4." I really don't want to buy the game on GOG. Any suggestions about wtf I'm doing wrong?
```

The subject line should not contain profanity or emotive language as it is unrelated and distracting to question, and can potentially evoke negative responses from those who might otherwise be helpful. Secondly, only one attempt at a solution has been made with no details besides the error message. To expand on the context of this question, this is a thread about the installation of a game overhaul mod for Fallout 4 after a patch had broken its implementation. Furthermore, there happens to be a detailed installation guide that the poster has made no reference to following, and this guide is contained within the very same thread. In addition, the thread contains many posts from the author complaining about the difficulty of installation, and not expanding their posts with meaningful information about the problem. This invites negative reactions rather than kind and helpful response from the more expert posters. As a direct result, the thread contains many answers that may or may not be related to the author's problem as well a considerable amount of mocking towards the original poster. Questions like this are better left unasked. 
## Conclusion

When asking intelligent questions, considering others time and efforts should be our top priority. We are, after all, at the mercy of their generosity to steer this very ship, and we should do well to remember that everyone finds their time just as valuable as we find ours. Furthermore, we should note the general principles and patterns of asking good questions so that our posts remain unlocked and answered for others to expand upon. For the sake of all, keeping our questions concise, courteous, and close-ended is conducive to everyone going home happy and humble. 
