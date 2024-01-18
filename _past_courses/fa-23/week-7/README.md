# Week 7
If you are behind and need help. Come to offer hours, contact the TAs, contact me about meeting up. We will be starting to move into project territory as this week is the last home work submission.
I am willing to drop the exam in exchange for more project work and project time, but I have to see improvement in the quantity of home work submissions. They will still be accepted late, but if we
don't get at least 80% submission rate for all work through HW 7 I will be forced to stick with the original plan of having a mid-term. This was previously laid out that there is a mid-term, my preference is to replace this with project work both in points and time to work on them as far as quality of output, but I have to be more confident you are getting what's going on and keeping up with where we are in order to do that. Exams assess working knowledge and right now it seems we need more focus on that working knowledge.

The material is not super easy, it's a lot of work, it's a lot of googl'ing, but we also have a lot of people to help and we took last week to stop and spend all of class doing open office hours. I said week one to anticipate around 10 hours of out of class work, this isn't just about showing up and working here. We are very available.

## Tues

## Critique

## "my code isn't building on vercel"
- Open WC changed... like a week ago
- after running `npm init @open-wc` make sure you select the `Application` option. This way there is a build routinee
### How to fix after the fact
- go to the folder JUST ABOVE the folder where you card is like `Documents/Github` if there is `Documents/Github/my-card`
- run `npm init @open-wc` again
- go through the options to build an application, ensuring you select `build` in the options presented (all the options except `lint`)
- when it asks about overwriting files, you'll want to NOT overwrite all of them, but you will want to overwrite package.json as it has changes required
- I can help you through this if you don't have a `build` command

- Live Crit: https://github.com/btopro/my-card-owen
- Live code: https://youtu.be/mVarAZyiUgU
  - adding stateful properties
  - adding slot
  - reflecting properties for design changes
- Refactoring a card based on what's been submitted  -- https://youtu.be/OJu30hh4qps
  - code: https://github.com/btopro/clothing-card

# Goals for this week's iteration
- Making our component / card reusable via properties, slots
- Buttons refactored to be stemming from the index.html while card is a stand alone component
- Published to NPM https://docs.npmjs.com/creating-and-publishing-scoped-public-packages
- Reusing code in code (this completes the development life cycle / feedback loop)

## Wed
- Look up how to setup npm so that you can publish code there
- `npm publish` which involves getting an account on npmjs.com

## Bringing code together
- Make a new repo (everyone does) with a new project done  via Open-WC
- Call this project `cards-app` because it's an app, with all your cards in it
- Pull in and `npm install` the work you did previously.
- Pull in the work of 1 other person in your pod from THEIR npm repo... OR.....
- If no one in your pod gets to this point, let's  pull in 2 things to use:
  - your own work (requirement)
  - my `meme-maker` tag -- https://webcomponents.psu.edu/?path=/story/media-memes--basic-meme (these same steps apply to if its someone else in your pod)

```
# install the tag so it's added to your package.json file
npm install --save @lrnwebcomponents/meme-maker

// top of your `cards-app/src/CardsApp.js` or whatever file is in src directory of this new repo
import "@lrnwebcomponents/meme-maker/meme-maker.js"; // use for your .js file

// in your render method
<meme-maker alt="Cat stalking a small toy" image-url="https://cdn2.thecatapi.com/images/9j5.jpg" top-text="I bring you" bottom-text="the death">
</meme-maker>
```
## What I did in class
- https://github.com/btopro/cards-app
- https://cards-app-one.vercel.app/
- https://www.youtube.com/watch?v=PedcMZihFbM

- This repo's `cards-app` element should have 3 import statements at the top of it. meme-maker (or a member of your pod), your own element, lit.
- the render method should have your card (without the buttons in it since those were just in the demo) + the other element
- this is the  feedback loop of modern development. Make something, resuse other things, reuse your own work.

## HW turn in to Canvas
- The above working, turned in on a Gist with links to  your code and your built code working (not a vercel.com.... address, the actual card rendered and working)
- power skim if not familiar with the concept of Atomic Design: https://atomicdesign.bradfrost.com/
  - I am not assessing on this but it's a very important foundational concept if you want to do this as a career. He basically invented the low level patterns by which everyone designs logical things that work together
- Read and answer the following: https://bradfrost.com/blog/post/the-design-system-ecosystem/
  - What are your take aways with regard to web components?
  - Are they here to stay? Is it the future? Is the future now? What would Brad say
  - What are some additional ways to make web components that Brad mentions? Link to some examples that we aren't covering in class.
- Watch the following again if you need help / review from before
  - https://www.youtube.com/watch?v=mxTYv_8EPIo
  - https://www.youtube.com/watch?v=waYp5pjp75Q
  - https://www.youtube.com/watch?v=HU8K4EyAncg
- Watch this to prepare for Project 1:
- https://www.youtube.com/watch?v=Ilw51giJWB0
