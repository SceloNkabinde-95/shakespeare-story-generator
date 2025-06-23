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

(Takes a Zoolander serious face pose): I was inspired by the challenge on https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Silly_story_generator#starting_point as I kept learning about Javascript and I thought "Wait a minute. I also recall using Markov Chains to create predictions in my other life, so why not use that to generate the stories of the great Shakespeare."

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

# Summarizing the phases of the project

## General Tools used

Before giving quick summaries of the phases, here's a list of more tools used (in addition to the skills listed above)

1. Visual Studio Code:

This is the home of many developers, so I decided to adopt myself into it to make my life easier. Almost all my coding was done using this bad boy; even the terminal itself was accessed using this.

2. Virtual environment for storing tech dependencies: 

Yes I know this isn't a tool itself but it's one of those important components for creating a project that's easily adaptable by others. Additionally, it is where most of the other listed tools are stored.

- In my project's folder, I simply booted up the terminal and used this command: python3 -m venv venv
and it was created.

3. Jupyter lab:

Like I said before. I come from a very analytics-facing background and our main aim there was to get results to our stakeholders and bosses as quickly as possible so we let the developers take care of the other techy stuff most often. Therefore, I opted for Jupyter lab because it really does fit the purpose in data analytics more than in development. Besides, ever since I was introduced to python it's been my go to IDE, and so I've grown fond of it.

- This was downloaded into the virtual environment via the command: pip3 install jupyterlab

- So whenever I need to use python I simply activate the virtual environment inside the project's folder and run: jupyter lab

## Phase 1: Extract speakers and speeches

In this phase we used the source as mentioned above (https://raw.githubusercontent.com/karpathy/char-rnn/master/data/tinyshakespeare/input.txt.) but limited the story such that there are only 5 unique speakers in total by copying all the dialogue until before a 6th speaker appears.

This is done so the project's complexity - especially when testing and validating - is easier to track.

By using this short form of the story, I imported the .txt file into python as a list and then extracted the speakers and speeches accordingly. The final result is saved in a dataframe with an extra column for the the speeches without any punctuation so the creation of transition matrices for speeches is based solely on the words.

## Phase 2: Create transition matrices

Once we have the final story stored in a dataframe format, we're ready to cook.

This phase kicks off with forming an algorithm that can take any list (a type of data in python) and dynamically determine the unique values therein before returning a transition matrix for probabilities of moving from one item in the list to another.

We then follow this by storing the speakers' sequence of appearance, taken from phase one's results, in a list format and then run it through the transition matrix algorithm. The results of this is saved in a file named speaker_transition_matrix.csv.

To end this phase we create one transition matrix for each speaker which is accomplished by first merging all the different speeches per speaker into one main list of speeches. Then we further combine the different speeches into an one itemed list of all the different speeches per speaker. This allows for creation of a list of all the words that for each speaker. Ultimately, we run these lists through the transition matrix algorithm. The results are stored in the files first_citizen_transition_matrix.csv, second_citizen_transition_matrix.csv, all_transition_matrix.csv, menenius_transition_matrix.csv, marcius_matrix.csv.

## Phase 3: Create a HTML webpage

In this phase, we create a rudimentary html webpage that has the simple html boilerplate structure and then we populate it with a title, placeholders for where the generated story's five speakers and their related speeches will be placed, and a button that will run the algorithm to generate the story upon clicking.

Our aim here is not to give a beautiful looking webpage at this stage, but only to ensure that the main functionalities of creating a randomly generated story on a webpage works. In a later state we will enhance the webpage so it's easy on the eyes.

## Phase 4: Apply the markov chain to generate the story

Generating a random story with five speakers using the markov chain has two stages to it - the first being the generation of the sequence of speakers, and the second is the generation of the appropriate and most probable speech by each speaker.

It is pertinent to note that the results of this phase are what we display as the story on the webpage. Thus, we use javascript to program these.

### How the markov chain process works

Before diving into the summary of this phase, here's an example of how the Markov chain process works:

Consider that we have three possible weather states that each day can have — **Sunny**, **Rainy**, and **Windy**. Suppose the probability of the weather changing from one state to another from one day to the next is defined as follows:

If the current state is **Sunny**:
- Probability of staying **Sunny** = 60%
- Probability of changing to **Rainy** = 30%
- Probability of changing to **Windy** = 10%

This can be written as:

| State | Sunny | Rainy | Windy |
| --- | ----- | ----- | ----- |
| Sunny   | 0.60  | 0.30  | 0.10  |

In fact, we can represent all transition probabilities in a matrix as follows:

| State | Sunny | Rainy | Windy |
| --- | ----- | ----- | ----- |
| Sunny   | 0.60  | 0.30  | 0.10  |
| Rainy   | 0.20  | 0.50  | 0.30  |
| Windy   | 0.30  | 0.30  | 0.40  |

Where:

Rows represent the current state

Columns represent the next state

###### Example: Forecasting 3 Days
Let’s assume that Day 0 is definitely Sunny.

###### Step 1: Setup the initial state vector (Day 1)

[S, R, W] = [1, 0, 0]

###### Step 2: Calculate the probabilities for Day 2

Sunny = 1×0.6 + 0×0.2 + 0×0.3 = 0.6
Rainy = 1×0.3 + 0×0.5 + 0×0.3 = 0.3
Windy = 1×0.1 + 0×0.3 + 0×0.4 = 0.1

New state: [0.6, 0.3, 0.1]

###### Step 3: Calculate the probabilities for Day 3

Sunny = 0.6×0.6 + 0.3×0.2 + 0.1×0.3 = 0.45
Rainy = 0.6×0.3 + 0.3×0.5 + 0.1×0.3 = 0.36
Windy = 0.6×0.1 + 0.3×0.3 + 0.1×0.4 = 0.19

New state: [0.45, 0.36, 0.19]

###### Summary

| Day | Sunny | Rainy | Windy |
| --- | ----- | ----- | ----- |
| 1   | 1.00  | 0.00  | 0.00  |
| 2   | 0.60  | 0.30  | 0.10  |
| 3   | 0.45  | 0.36  | 0.19  |

This process of computing the next state based on current probabilities and a fixed transition matrix is called the Markov Chain Process. We apply this iterative approach across both stages of our model.


### Phase 4 Stage 1: Getting the sequence of the speakers

The algorithm in this stage uses the transition matrix speaker_transition_matrix.csv to determine what the probability to move from one speaker to another is.

By using a random number between 1 and 5 to pick out the first speaker in the list of the speakers (where First Citizen correlates with 1, All correlates with 2, Second Citizen correlates with 3, Menenius correlates with 4, Marcius correlates with 5) we determine the probabilities to move to the next speaker and then pick the speaker with the highest probability as the next speaker in the same way as the example above. Thereafter we repeat the process while ensuring that we don't pick anyone who was picked before - we do this until we've exhausted the list.





