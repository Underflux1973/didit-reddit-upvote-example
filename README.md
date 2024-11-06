REFLECTIONS:

I will try to remain objective about this exercise even though today has felt very deflating. The reality is that I have never been able to deploy successfully onto Vercel on previous assignments so I have always felt that I don't know how to connect the dots and am missing some vital bit of information, which is fairly frustrating.

I have provided some screenshots of the logs and deployment errors in the public files.

1. The main error occuring is a ECONNREFUSED which indicates that my database isn't recognising the connections made in the code so the first thing I did was to check the environment variables. I double checked the Database URL, the password as well as the GitHub Auth ID and Secret. I reset them all and started from scratch but to no avail.

2. I then realised after doing some research that I needed to add the API keys to the Vercel deloyment as the Environment variables in my .env file are local variables so Vercel needed server environment variables - the ANON KEY and SECRET. I tried adding these into the Vercel environment variable section but it didn't allow due to incorrect format.

3. Additionally I really wasn't sure about the need to install the Supabase librairies or further code to import Supabase in the config file. I essentially ran out of time as per usual.

4. I clearly don't understand this on a fundamental level so its difficult for me to see the positives about this currently, especially when you see many other colleagues finishing and completing the task at hand.

## Upvote

Upvote is a Reddit-esque web application that allows users to create posts, upvote and downvote posts, and comment on posts in a multi-threaded, nested list.

The project is built using Next.js with the /app router and [Tailwind CSS](https://tailwindcss.com/), and uses [Auth.js (formerly Next Auth)](https://authjs.dev/) for user authentication. The data is stored in a Postgres database, which is created and accessed with raw SQL queries using the `pg` package.

The project is a work in progress and is not yet complete.

## Features

- [x] View a list of posts
- [x] View a single post
- [x] Create a post
- [x] Upvote and downvote posts
- [x] Pagination of posts
- [x] Comment on posts
- [x] Nested comments (recursive lists)
- [x] User authentication

## Setup instructions

1. Fork the repository (check "copy the main branch only") and clone your fork to your local machine
2. Run `npm install`
3. Create a `.env.local` file in the root directory and add the following environment variables:
   - `DATABASE_URL` - the URL of your Postgres database (eg. the Supabase connection string)
   - `AUTH_SECRET` - the Next Auth secret string (this can be anything at all like a password, but keep it secret!)
   - `AUTH_GITHUB_ID` - the GitHub OAuth client ID (create yours in [Github developer settings](https://github.com/settings/developers)
   - `AUTH_GITHUB_SECRET` - the GitHub OAuth client secret (create this in [Github developer settings](https://github.com/settings/developers))
4. Create the database schema by running the SQL commands in `schema.sql` in your database (eg. by running the commands in Supabase Query Editor)
5. Run `npm run dev` to start the development server
6. Open [http://localhost:3000](http://localhost:3000) with your browser to see the site

## Potential future features

- [ ] User profiles
- [ ] Sorting posts by recent (date posted), top (most upvotes), and most controversial (most upvotes _and_ downvotes)
- [ ] User karma scores
- [ ] User badges / trophies (awards for achievements like number of posts, years on the site, etc.)
- [ ] User settings (eg. number of posts per page, theme, etc.)
- [ ] Moderation tools / reporting or flagging objectionable comments for removable by admins
- [ ] Searching posts (possibly using simple SQL LIKE '%some search%', or [Postgres text search](https://www.crunchydata.com/blog/postgres-full-text-search-a-search-engine-in-a-database))
- [ ] Subreddits (separate communities, that isn't just one big list of posts, that can be created by users)
- [ ] User notifications
- [ ] User private messaging
- [ ] User blocking
- [ ] User following
- [ ] User feed (posts from users you follow)
- [ ] User flair
