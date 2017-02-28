
### DEVELOPMENT

During development there are 3 pages you might be interested in.
 - The root page is there to display the documentation.
 - The `/demo` page is there to display various demos for how to use your component.
 - The `/implementation` page, is a sandbox where you can work with less noise compared to the demo page.

**Running Your Project**

 - `npm start` is the default command to spin your project. It will clean up any old builds
 and then start up a development server on port `3000`  using [Browsersync](https://www.browsersync.io/) to reload the page when changes occur.

**note:** If you are finding that when reloading it is switching from demos back to docs, then in the browser add the route `/demo` to the url and then the refreshes will happen on that route.

<% if (elementVersion === '2.0') { %>
 **note:** Make sure you are using [Chrome Canary](https://www.google.com/chrome/browser/canary.html) for development
<% } %>

**Deploying your Project**

- `npm run pages` is the command to deploy a [Github Pages](https://pages.github.com/) site for your project 
<% if (gitAccount === 'personal') { %> - [<%=elementName%>](https://<%=orgName%>.github.io/<%=elementName%>) <% } else { %>
[<%=elementName%>](https://<%=gitRoot%>.com/pages/<%=orgName%>/<%=elementName%>)
<% } %>


**note:**
  - This creates a orphan branch with no history.
  - Always run this from `master` after pulling the latest build to ensure your docs reflect
  the most recent version.

**Testing Your Project**

- `npm run test` is the command to run basic tests using [Web Component Tester](https://github.com/Polymer/web-component-tester) in the terminal.

Automated testing is also supported with [TravisCI](https://travis-ci.org/getting_started). If you enable this feature on the Github repo then tests are set to run on every commit. This can be adjusted in the `.travis.yml`<% if (sauceLabs === true) { %>

We also support greater cross browser support with testing from [SauceLabs](https://saucelabs.com/). These are currently built to run on every pull request.

To add more VMs to `wtc.conf.json` if you would like to increase your cross browser coverage.
<% }%>


### USAGE

- **Installation**
  - `bower install <%=orgName%>/<%= elementName %>`

<% if (sauceLabs === true) { %>
### FAQ

###### SauceLabs Setup.
If you already have an account then all you need to do to get SauceLabs working is:
- Install the travis command line module (if you haven't already)
    - gem install travis
- `travis encrypt SAUCE_USERNAME=[your username] --add`
- `travis encrypt SAUCE_ACCESS_KEY=[your access key] --add`
- Commit and push .travis.yml
- You're done!
<% }%>