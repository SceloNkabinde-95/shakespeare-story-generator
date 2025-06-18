# What is this about?

Well... the main goal of this project is to create a web page that generates random stories in a shakespeare esque format. 

In fact, the very source of the words and characters will be from a pseudo-shakespeare-story as is seen in this blog-post https://raw.githubusercontent.com/karpathy/char-rnn/master/data/tinyshakespeare/input.txt. In it Andrej Karpathy creates a 40 000 line story from different Shakespear's plays as a result of "The Unreasonable Effectiveness of Recurrent Neural Networks" (how ironic right?).

In effect, the random story that will be generated will be second-degree murder of the actual stories (sorry, not sorry).

# Okay, why are you doing this?

Uhmm... Coz I wasn't loved as a child. (Just kidding!)

I'm currently upskilling my web dev skills and I think I have the fundamentals figured out and so I want to prove that to myself. 

Additionally, coming from a data analytics background I think it'll be cool to show you guys that I have other skills sometimes (wink wink).

# Wow dude, you're so amazing! What inspired you?

I don't like to toot my own horn but I know I'm the best :)

(Takes a Zoolander serious face pose): I was inspired by the cjallenge on https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Silly_story_generator#starting_point as I kept learning about Javascript and I thought "Wait a minute. I also recall using Markov Chains to create predictions in my other life, so why not use that to generate the stories of the great Shakespeare."

At that point I came across Pushpendra Singh's similar Markov Chain's project found here https://medium.com/@pushpendrasinghcod/text-generation-from-shakespeare-play-using-markov-chains-eee5bfcbb7a0, and then I knew that this has to be done. My hands are tied now, so here we go!

# So what's needed (skills) to make this a real thing?

## None technical

1. Project breakdown and continuous agile updates along the journey: 

Since the project is mostly from an goal that isn't clearly laid out, one needs to be able to breakdown the goal into different parts and then keep updating the sup-parts into small chuncks of attainable actions. Then as those sup-parts evolve, the skill of being agile and patient is most crucial for completion of each task.

2. Research:

One needs to be able to ask the right questions and keep altering those until they get what they need. So the skill of researching (or shall I say investigating) is not a nice to have but a must have.

Within this skill, I give a shout out to google and any conversational AI tool (such as chatgpt) because they make this skill somewhat of a breeze.

3. Grit and Persistence:

Yep. That's here as well. 

Without these the project is almost impossible to start or to do when one meets hurdles along the way. With all the technical skills put together, there is no doing of any task with these.

## Technical

1. Markov Chain Knowledge:

At a high leve, this skill is set out to find a transition matrix which determines probabilities of moving from one speaker to another and for each speaker this requirement determines probabilities to move from one to another - all based on the source story.

2. Python:

To do data extraction and manipulation of the story in such a way that one is able to create final transition matrices requires use of python and relevant libraries such as pandas.

3. HTML, CSS and Javascript:

The final website will certainly need structure and some styling so mere humans like myself can see clearly where the button(s) to generate the story is and html, css and javascript are here for that.

4. Git and Github:

These are probably the best places to store every instance of progress made on the project. Additionally, if anyone ever wants to contribute (me willing, of course) these tools will make sure those contributions fit like a glove in this project.

## A final note on skills

The lists above are exhaustive and even within each of them there's other layers like data analytics within python and creation of functions and events within javascript. However, the skills highlighted show the high level knowledge and attributes that will have one at the least start with the project.

# Project roadmap please

This project has five main phases:

1. Extract the speakers and their relevant speeches from the story.

2. Create a transition matrix for speakers and one transition matrix for each speaker's speeches (the words thereof).

3. Create an html webpage for generating a story at a click of a button (or buttons).

4. Use results of transition matrices in an algorithm that generates random stories.

5. Put it all together and test and update as needed.