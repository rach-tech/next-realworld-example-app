# ![Next.js + SWR Example App](project-logo.png)

# Sonarcloud
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=rach-tech_next-realworld-example-app&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=rach-tech_next-realworld-example-app&metric=security_rating)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)
[![Vulnerabilities](https://sonarcloud.io/api/project_badges/measure?project=rach-tech_next-realworld-example-app&metric=vulnerabilities)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)
[![Code Smells](https://sonarcloud.io/api/project_badges/measure?project=rach-tech_next-realworld-example-app&metric=code_smells)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)
[![Lines of Code](https://sonarcloud.io/api/project_badges/measure?project=rach-tech_next-realworld-example-app&metric=ncloc)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)
[![Technical Debt](https://sonarcloud.io/api/project_badges/measure?project=rach-tech_next-realworld-example-app&metric=sqale_index)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=rach-tech_next-realworld-example-app&metric=reliability_rating)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)
[![Duplicated Lines (%)](https://sonarcloud.io/api/project_badges/measure?project=rach-tech_next-realworld-example-app&metric=duplicated_lines_density)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)
[![Bugs](https://sonarcloud.io/api/project_badges/measure?project=rach-tech_next-realworld-example-app&metric=bugs)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)
[![Quality gate](https://sonarcloud.io/api/project_badges/quality_gate?project=rach-tech_next-realworld-example-app)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)
[![SonarCloud](https://sonarcloud.io/images/project_badges/sonarcloud-white.svg)](https://sonarcloud.io/summary/new_code?id=rach-tech_next-realworld-example-app)


# deepsource
[![DeepSource](https://deepsource.io/gh/rach-tech/next-realworld-example-app.svg/?label=active+issues&show_trend=true&token=r6ZUfN_A2Un-0HoHBV2K1ftb)](https://deepsource.io/gh/rach-tech/next-realworld-example-app/?ref=repository-badge)
[![DeepSource](https://deepsource.io/gh/rach-tech/next-realworld-example-app.svg/?label=resolved+issues&show_trend=true&token=r6ZUfN_A2Un-0HoHBV2K1ftb)](https://deepsource.io/gh/rach-tech/next-realworld-example-app/?ref=repository-badge)


> ### Next.js + SWR codebase containing real world examples (CRUD, auth, advanced patterns, etc) that adheres to the [RealWorld](https://github.com/gothinkster/realworld-example-apps) spec and API.

### [Demo](https://next-realworld.now.sh/)&nbsp;&nbsp;&nbsp;&nbsp;[RealWorld](https://github.com/gothinkster/realworld)

Originally created for this [GH issue](https://github.com/gothinkster/realworld/issues/336). The codebase is now feature complete; please submit bug fixes via pull requests & feedback via issues.

We're currently working on some docs for the codebase (explaining where functionality is located, how it works, etc) but most things should be self explanatory if you have a minimal understanding of Next.js/SWR.

## Getting started

You can view a live demo over at [https://next-realworld.now.sh/](https://next-realworld.now.sh/)

To get the frontend running locally:

- Clone this repo
- `npm install` to install all dependencies
- `npm run dev` to start the local server

### Making requests to the backend API

For convenience, we have a live API server running at `https://conduit.productionready.io/api` for the application to make requests against. You can view [the API spec here](https://github.com/GoThinkster/productionready/blob/master/api) which contains all routes & responses for the server.

The source code for the backend server (available for Node, Rails and Django) can be found in the [main RealWorld repo](https://github.com/gothinkster/realworld).

If you want to change the API URL to a local server, simply edit `lib/utils/constant.js` and change `SERVER_BASE_URL` to the local server's URL (i.e. `localhost:3000/api`)

## Functionality overview

The example application is a social blogging site (i.e. a Medium.com clone) called "Conduit". It uses a custom API for all requests, including authentication. You can view a live demo over at [https://next-realworld.now.sh/](https://next-realworld.now.sh/)

**General functionality:**

- Authenticate users via JWT (login/register pages + logout button on settings page)
- CRU\* users (sign up & settings page - no deleting required)
- CRUD Articles
- CR\*D Comments on articles (no updating required)
- GET and display paginated lists of articles
- Favorite articles
- Follow other users

**The general page breakdown looks like this:**

- Home page (URL: /)
  - List of tags
  - List of articles pulled from either Feed, Global, or by Tag
  - Pagination for list of articles
- Sign in/Sign up pages (URL: /user/login, /user/register)
  - Use JWT (store the token in localStorage)
- Settings page (URL: /user/settings )
- Editor page to create/edit articles (URL: /editor/new, /editor/article-slug-here)
- Article page (URL: /article/article-slug-here)
  - Delete article button (only shown to article's author)
  - Render markdown from server client side
  - Comments section at bottom of page
  - Delete comment button (only shown to comment's author)
- Profile page (URL: /profile/username-here, /profile/username-here?favorite=true)
  - Show basic user info
  - List of articles populated from author's created articles or author's favorited articles

<br />

[![Brought to you by Thinkster](https://raw.githubusercontent.com/gothinkster/realworld/master/media/end.png)](https://thinkster.io)
