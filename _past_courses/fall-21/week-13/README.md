# Week 13
## Tuesday - I was out sick; free working day

## Thursday
- Review work submitted, providing feedback and critique
### 3b4b
- Wow. Fantastic start visually. Right on track with lots to do but really good direction.
- Think of how you're going to approach this responsively. I joked a bit about animation of things (tho cool if it did ;) ) but it should at least scale proportionally to ~ 400px. Try to envision how it looks / does this on phone, tablet, laptop and big screen TV type sizes (find break points for these that are reasonable. usually like things like 400, 800, 1200, 1440+ but find better values)
- Watch for a11y considerations around alt default values. For example: `this.alt = "Stamp";` should be `="";` as its a decorative image. Same w/ photo (tho need props to allow user implementing this to define at top level card implementation like photo-alt)
- label, to and from should be translatable strings. Not sure user needs to be able to override them (card has as props currently) see i18n post from last week
- good, effectively slots. make sure to implement more example content for them in demo
- make sure there's the ability to override the locations variable `INSERT-LOCATIONS-HERE` via props passed down from card (same w/ stamp, postmark, photo)
- Another possible way to do the photo is a slot in card that's passed down to right place. `::slotted(img)` instead of `img` in that will allow same thing but as long as can be modified via props not a big deal
- Make sure to run a Lighthouse Audit (this is relevant to everyone) as it gives great feedback that's often easy to implement. For example your stock images are nutzo sizing. Should at least be smaller JPGs
![lighthouse score](https://user-images.githubusercontent.com/329735/142298185-f2178b0f-5f26-4d95-b9ae-cdac1cdca0bf.png)
### PenStat
- Great progress with a lot of functionality already built in and design is starting to match comp
- for font color when using simple-colors, do this: `color: var(--simple-colors-default-theme-grey-12);`. This will fix your color contrast when `dark` mode is activated. This is how we *gaurentee a11y* when it comes to visual contrast. background-color some low number, text color high number grey (then dark flips it)
- `.backgroundbox` can also pick this color up and pass accentColor down across things that need to utilize the appropriate CSS variables
- very cool on the translation being pegged to voice dialect change. Make sure this is a boolean for `speak` or something so that it shows a little icon-button for a speaker. Clicking it then does the speach as opposed to when you test correctness. It could be a form of hint or even a review mode where it's speaking them to me. Speech synthesis API could then be used to push a button to test your voice input against what it is (this was clearly a joke just to mess with you. I mean, you couldn't just create your own duo-lingo app like this for free... could you.... could you....)
- Very creative block but this shouldn't be in the super.firstUpdated conditional block of logic
```js
if (propName === 't') {
  this.i18store = window.I18NManagerStore.requestAvailability();
  this.speech.lang = this.i18store.lang;
  console.log(this.speech.lang);
}
```
### table-in-the-corner
- Great prototype of drag and drop of 2 items
- in the simple-icon project repo there's a simple-icon-button-lite in the event you want something with built in clickability / a11y to avoid wrapping in another button tag. (not a requirement, just offering as a time / consistency saver here)
- Looks like your trying to get the dynamics down of sortable-option and applying events in the sortable-frame which is a good place to be. next shoot for having those supplied in the light dom of the `sortable-frame` tag.
- In this setup; instead of using the `@dragstart` handler, you can loop through the light dom children when the element sets itself up and apply the drag event handling there. OR. the sortable-option could apply this to itself automatically. Especially since dragStartHandler is a global event piece of data via the dataTransfer object your using
- Similarly, you could probably have the drop functionality be in the item itself, in which case the tag use the same `event.target` data and replacement logic to basically just insert the item ahead of itself as they'll have the same parent.
- It's up to you how you want to envision it but the frame as a controller to ensure nothing bad leaks in, could also be that items in light dom are ANYTHING and then the frame will loop through children and convert them into data in some manner to render as options, or to wrap those options in the sortable-option tag.
- If you went the wrap route you'd have A LOT of flexibility in how this coul dbe used; it could be paragraphs, or images, or basically anything that would then be able to be reordered.
- In order to do the buttons up and down; the 1st option of the parent disables the up arrow, last option disabled the down arrow
- When button clicked to go up or down, emulate the drag and drop functionality by detecting item ahead or after current and then inserting before or after
- I'd also make something more semantic than sortable-frame. Maybe like sortable-question or something since frame isn't very descriptive to someone reading it as implemented code.
- Make sure question is a variable as far as what's asked
### viable-slime
- Damn. This is fantastic.
- https://www.youtube.com/watch?v=Ok_Qn36st3U
- This will get a deep dive in class w/ write up before.
- https://github.com/btopro/slime-the-web

### nothing to review / worth reviewing yet
- IST402Group1
- IST402-Group-F
- ist402groupj
- PaddysHub
- Group k / IST402
- TheKodingKrab
- runtimeerrorsmadeeasy

### Quick tutorial to run through on own time after introducing concept
- [Reading to start understanding haxProperties wiring](https://dev.to/btopro/understanding-haxschema-the-api-powering-our-editor-2ln6)
  - There's example wiring in the element repo I gave you
  - When you modify your tag name, you'll need to update the associated reference in when we call "appstore" specification to make it register correctly in the HAX demo space your repo ships with. Namely this line will need updated -- https://github.com/elmsln/project-3/blob/master/assets/appstore.json#L4
  - After break I'll go into more detail about wiring and how it works for examples but you can see in the blog post a deep dive on how an individual property can be mapped using the `inputMethod` that makes sense.
  - Think of this like StorybookJS knobs.
- [MutationObservers example code pen](https://codepen.io/dayvidwhy/pen/egdZyY?editors=1111) (hit console button in codepen to see what's happening)
  - Mozilla docs - https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver
  - change in DOM structure below an item generates a change record / specialized event
  - Could be used to detect when lightdom children are added or changed in a more flexible manner
  - possible example: drag and drop to reorder children would change node order, would be a mutation
  - Mutations can happen on attributes, nodes (order, adding / removing), children of nodes / whole tree, or textNode changes (characterData)
  - Important to do data clean up for memory / performance reasons
## Group activity
- sharing progress and providing feedback to teams developing same element as you
- All groups working on same element move to same area
- 1/2 of group move left, 1/2 stay; only within the teams working on the same problem
  - Conference badge people group up with trading card people
  - click the words people group up with sort the words people
- Share your repo w/ another team
- switch laptops or clone and setup their project locally to review code
- Each group should be looking through code of the other group at the same time
- Create an issue that has at least 5 recommendations for how they could improve their element overall at a code level (CSS, JS logic, or HTML structure) or additional things to include as per [project directions](https://github.com/elmsln/edtechjoker/tree/master/fall-21/projects/p3-haxtheweb)
- The issue should include any problems that you helped talk through with the other team (like if they are stuck on how to solve something, you showed a possible solution, gave advise, and visa versa)
- Post a link to the issue queue of each project at the end of class. There should be at least 2 issues posted in each queue.
- This is class participation for today
- Come back together with your group and discuss / work on project more

## Homework
- Read https://dev.to/btopro/understanding-haxschema-the-api-powering-our-editor-2ln6 to understand how HAXSchema can be written to allow your asset to talk to the HAX editor.
- Project check in 3 is due the Sunday after Thanksgiving Nov 28th
- This is a simple status update
- What your group got done since last check in (so last week + whenever else you work)
- What insights you gained from the class activity to implement
- What your next steps are?
- Your design should be taking shape
- Your logic layer should be starting to come together
- You should at least take a stab at modifying the haxProperties HAXSchema to map to your element and understand that relationship
- `TEAMNOTES.md` updated to reflect the above + code to actually back up that your not writing things like "we talked a bunch" as I read these and am not dumb.
- **7 groups currently lack these in a way that I can review. This is not my problem even if it wasted an hour I could have spent with my kids. It's your problem as this is 20% of the course grade.**
