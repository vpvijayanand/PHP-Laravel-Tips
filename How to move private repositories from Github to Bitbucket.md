---
title: How to move private repositories from Github to Bitbucket
tip-number: 9
tip-username: Vijayanand
tip-username-profile: https://github.com/vpvijayanand
tip-description: How to move private repositories from Github to Bitbucket.

---
How to move private repositories from Github to Bitbucket
Github is a great service and remains the epicentre of open source code. But for a single developer paying for private repositories, its payment plans don't make a lot of sense. This is because they charge by the number of repositories you have. I tend to have quite a few small private repos for various projects, so the cost creeps up pretty quick. I have absolutely no objection paying Github for private repos, but the pricing structure does need to be sensible.

Bitbucket's pricing structure makes a lot more sense. They charge by the number of users, rather than repositories. As a bonus, it is free for up to 5 users. And you get unlimited repositories, a price increase is only triggered by an increase in the number of users. This makes a lot more sense than charging my repositories because it better reflects the size of the organisation. A large organisation with more users will pay more, a smaller organisation with less users will pay less and a single developer will pay nothing without being constrained by the number of repositories. Makes sense right?

Like I said before, I don't mind paying. The fact that bitbucket give it to me for free is a bonus.

Moving repos from Github to Bitbucket
Now down to the meat of this post - how to actually move your private repositories from Github to Bitbucket!

Import from Github to Bitbucket
In Bitbucket on the top menu, click Repositories and then Import Repository Fields for importing existing code from Github
Select Git
Select 'Require Authentication'. Add the username and password from your github account. Note: You will get an authentication denied error anyway, which you can ignore.
Copy the URL from your Github account. This should be https://github.com/USERNAME/REPONAME.git. This can be found in the right hand column under HTTPS URL of repository on Github
Add the URL you copied in step 4 to URL field in Bitbucket
The fields under New repository will be automatically filled in, including the Name. If you want to change the name and add a description, you can do so here. Fields for the new repository in Bitbucket
Click import repository.


