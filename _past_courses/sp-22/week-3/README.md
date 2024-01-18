## Week 3 - Microservices and further exploring our first API access project
- Skimmed in class; read to gain context of the semester: https://divante.com/blog/10-companies-that-implemented-the-microservice-architecture-and-paved-the-way-for-others/

## Tuesday
- Looking over what people produced and pointing out relevant things / unpacking certain issues
- I'll give feedback on a few solutions and dig into them in more detail; at least 1 of each option / role
- Option 1:
  - https://github.com/mayormaier/api-project-1/blob/master/src/UserIP.js
  - https://github.com/Taylor-Bracone/api-project-1/blob/master/src/UserIP.js
  - https://github.com/SLDSO/api-project-1/blob/master/src/UserIP.js
  - https://github.com/TaylorMorini/api-project-1/blob/master/src/UserIP.js *
- Option 2:
  - https://github.com/juliansim1729/api-project-1/blob/master/src/LocationFromIP.js
  - https://github.com/zjohnson10/api-project-1/blob/master/src/LocationFromIP.js
  - https://github.com/Aiden-Brook/api-project-1/blob/master/src/LocationFromIP.js
  - https://github.com/aaronlienhard/api-project-1/blob/master/src/LocationFromIP.js
- Option 3:
  - https://github.com/hayden-angello/api-project-1/blob/master/src/response.json
  - https://github.com/jforcina20/api-project-1/blob/master/src/response.json
  - https://github.com/hvk5388/api-project-1/blob/master/src/response.json
- Bonus wiring:
  - https://github.com/liljimmyk99/api-project-1/blob/master/index.html#L70 *
  - https://github.com/reyes-edwin/api-project-1/blob/master/src/LocationFromIP.js#L71-L76 *
  - https://github.com/mayormaier/api-project-1 *
- Grouping to ensure everyone is sitting near group members for the semester
- In class activity reviewing each other's code and making a single repo
- Looking at npmjs.com, my own library of elements our team makes and how we can leverage existing work to buid new work
  - Bringing in wikipedia-query and at least putting it in our repo / dependencies via package.json or CLI method
  - Example being used in a codepen - https://codepen.io/btopro/pen/yLNmVbw
  - Source: https://github.com/elmsln/lrnwebcomponents/blob/master/elements/wikipedia-query/wikipedia-query.js
  - npm: https://www.npmjs.com/package/@lrnwebcomponents/wikipedia-query
  - more info on bare imports: https://blog.logrocket.com/es-modules-in-browsers-with-import-maps/
- Establishing the starting point for Lab 3 that expands upon this same project.
- In class group activity:
  - exchange contact info / make a multi-person DM on slack or whatever space of your choosing
  - 1 of the PM / API product owners, Create a github organization and add everyone in your group to it (ensure you discuss who's doing this / spot check while 1 person "drives" so to speak)
  - Also make sure you grant roles within the organization to everyone added so that they can adminster the projects of the org!
  - In that organization, use the following "template" to create a starting point for everyone to work on: https://github.com/elmsln/ip-project
  - Templates are like forks but don't retain `.git/` history. It's more of a starting point than a continuation.
  - All members should fork this repo in their organization to their personal account so they have a copy (or if you know how to and want to work in branches you can as well but I won't be covering this)
  - Make sure everyone on your team has a fork of the repo and then has it cloned locally on their machine
  - `npm install` and `npm start` to ensure everyone has everything running properly
  - Using the feedback from class, partners in front-end, back-end, and API/Owner will work together to improve their Option to be the best it can be
  - Each pair will use 1 person's fork; 1 "driving" (aka coding) the other pair-programming / over the shoulder / helping google / toubleshoot as needed
  - When the solution to each option works in a team member's fork, commit it back to the fork of `ip-project` for your organization
  - If you hit this bullet point before the end of class, start into the "activity" for thursday. The faster you get Thursday done, the more time to work on the homework in class!

## Wednesday
- Get the above cleared up as needed
- dream about being in class
- imagine what the sun feels like on your face as the cold breeze blows through the trees
- "Is this really happening... am I still going to class?" - yes, the voice in your head answers
- you look around in euphoria, "I... I've never been to class this many weeks in a row without disruption..."
- You panic... "am I actually still dreaming... did I just pass out in the zoom of another class at my desk.. what is this"
- You wake up... alone, the zoom meeting has ended. It's been hours since you "had class", you must have slept through it all
- Egerly, you await the resuming class with humans

## Thursday
- In class group activitiy:
  - Issue a Pull Request (Github UI thing) and make sure the PM / whoever owns the repo accepts it
  - This will pull all 3 solutions into a single, agreed upon repository
  - The goal is to get a working Repo that has all 3 options merged together into one after discussing with your partner / teammates
  - After this happens, all teammates should get a UI that looks like this in their fork of the repo
![Github UI for rebase](https://user-images.githubusercontent.com/329735/150425002-e8e06bbc-daa6-4f03-bf0a-ceb38a6a2954.png)
  - Rebase your personal repo so that everyone is back on the "same page". All repos for all teammates will now have the same code.
  - local machine: `git pull origin master` and now you have the assets back local again and in sync
  - if you run into issues with git: VSCode's git integration is well done
  - Also https://desktop.github.com/ while not required, can at times help resolve issues in getting code all merged back together

## Homework / Lab
- Read this article / watch the talk at the bottom to gain insight into how these things are built out and contextually leveraged, at scale: https://divante.com/blog/10-companies-that-implemented-the-microservice-architecture-and-paved-the-way-for-others/
  - We're working in a small, some what silly way for sure, but realize that this pattern just replicates and larger complexity is just smaller complexity multiplied
- now you're going to try adding another element that leverages 1 API and routes the data through to the usage of this tag
- Edit the `src/LocationFromIP.js` file in order to try adding the following:
- Create an HTML link that sits below the iframe that links to the location on google maps.
- google maps links can be formed like this: `https://www.google.com/maps/@40.804,77.910,14z` where it's `@long,lat`. The `,14z` is needed for "Zoom level"
- When we get the data back on long / lat, also pull the City and State at this time
- Using this information, wire the data up to a wikipedia-query tag so that when the IP changes, the Location Changes, the Wikipedia article changes
  - This is a silly example of 3, unrelated web service APIs, all feeding each other info. Microservices do this all the time like get GPS location, calculate speed, etc
- It'll need to be added as a dependency if you didn't already https://www.npmjs.com/package/@lrnwebcomponents/wikipedia-query (and then `npm install`)
  - `@lrnwebcomponents/wikipedia-query`
  - Read up on "saving" things that you add as dependencies -- https://www.stackchief.com/tutorials/npm%20install%20%7C%20how%20it%20works
  - You can also manually edit the `dependencies` section of your `package.json` but ensure you don't break the `json blob` in doing so :)
- Then you'll need to `import` the tag at the top of your file to use it (see how the other files `import` assets for usage`)
  - The path to referencing wikipedia-query is `@lrnwebcomponents/wikipedia-query/wikipedia-query.js` as a "bare import"
  - "bare import" refers to NOT having a reference to where the file lives. We always allow node to help interpret where it lives
- Then in your `render()` method you'll have to implement the tag. Here's some example usage:
  - https://codepen.io/btopro/pen/yLNmVbw
- The `search` property in a common named city. it takes city`, ` state and the comma then a space are important to the call working
- Leverage this tag in your element three times, like I have in the codepen. 1 that does the `city, state` and another that's just `city` and another that's just `state`
  - To test accuracy, if you have a VPN or Cellphone see if you show up in a different city if it still works (it should)
  - **note**: We presently don't have a "that didn't work" fail test in querying the wikipedia API so if you say VPN to new york and put in `New York, New York` it returns nothing vs `New York` is the state while `New York City` is the result you probably would assume to be there. I say this because if you move around to other spaces they might not always work for all 3 tags, so we're basically leveraging each to illustrate reuse of an API + reuse of a visual asset

## Submitting the lab
- A blog post this week; each Option / Role covers a different API in what we've put together but all options should cover the following:
- Screenshots / video (optional) conveying what the tag is, how it works to visualize the API data
  - While not required, screencasting might be a lot easier for this one but it's entirely up to your preference / creativity levels / desires
- Talk about how `fetch` can be used to get information from the API and feed it into a `LitElement` based web component to provide the stateful updating of the DOM
- markdown block using the ` ` ` 3x in a row as a code block to illustrate the JSON API response
- Links to the service in question so that people can learn more about the API if they want
- Links to your source code on github so people could poke at the code more to learn about it (link to which ever element your writing about below)
  - the links and in-class assignment effectively serve as the backdrop for your blog post. Blog post doesn't make sense? Real easy to tell who didn't do the lab.

### Option specific parts
- **Option 1 - Front end Devs** - You are writing from the perspective of the IP address / location API element and how the IP address was fed into the API of the GeoIP to detect the Long / Lat coordinates
- **Option 2 - Back end Devs** - You are writing from the perspective of the GeoIP element and taking the Long / Lat data to obtain the Google Maps iframe, link and wiring into the `wikipedia-query` tag
- **Option 3 - API / Product Owner** - You are writing from the perspective of the wikipedia API itself and leveraging it via `wikipedia-query`. You'll be talking about how this API works and how when given a City, the API is able to render the data of the article about it.
  - Wikipedia's API is documented here -- https://en.wikipedia.org/w/api.php
  - wikipedia-query source for a backdrop of code you can walk through - https://github.com/elmsln/lrnwebcomponents/blob/master/elements/wikipedia-query/src/wikipedia-query.js#L82

- Drop a link to your blog post into the #edtechjoker slack channel when finished
- **each teammate is writing their own article from the option perspective in question and each person should have their own repo w/ code as the backdrop to their article**

### Pro tip
- remember you can hit inspect -> Network tab and when the page loads see the call go off to all 3 of the APIs to see them happen / get the data structure
  - This will allow you to complete the above writing assignment even though you didn't write this tag :)
