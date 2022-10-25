# 100Devs Directory

A developer directory built on [Next.js](https://nextjs.org/) and [MongoDB Atlas](https://www.mongodb.com/atlas/database), deployed on [Vercel](https://vercel.com/) with the [Vercel + MongoDB integration](https://vercel.com/integrations/mongodbatlas).

![](#)


## Deployment Instructions

After forking or cloning this repo, you will need to create a [GitHub OAuth App](https://docs.github.com/en/developers/apps/building-oauth-apps/creating-an-oauth-app) to use it. Here are the steps:

1. Go to https://github.com/settings/developers and create a new OAuth application
2. Name your application whatever you want.
3. Set the homepage URL to **`https://vercel.app`** for now (we'll change this later).
4. Set the authorization callback URL to **`https://vercel.app/api/auth/callback/github`** for now (we'll change this later).
5. Click "Register Application."
6. Once the application is created, copy the "Client ID." This will be your **`GITHUB_CLIENT_ID`**.
7. Generate a new client secret and copy that too. This will be your **`GITHUB_CLIENT_SECRET`**.
8. Generate a random secret [here](https://generate-secret.vercel.app/32). This will be your **`NEXTAUTH_SECRET`**.
9. Click on this button below to clone and deploy this template to Vercel.

  [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fvercel%2Fmongodb-starter&project-name=mongodb-nextjs&repository-name=mongodb-nextjs&demo-title=MongoDB%20Developer%20Directory&demo-description=Log%20in%20with%20GitHub%20to%20create%20a%20directory%20of%20contacts.&demo-url=https%3A%2F%2Fmongodb.vercel.app%2F&demo-image=https%3A%2F%2Fmongodb.vercel.app%2Fog.png&integration-ids=oac_jnzmjqM10gllKmSrG0SGrHOH&env=GITHUB_CLIENT_ID,GITHUB_CLIENT_SECRET,NEXTAUTH_SECRET&envDescription=Instructions%20on%20how%20to%20configure%20these%20env%20vars:&envLink=https://github.com/vercel/mongodb-starter/blob/main/.env.example)

10. Once your application is deployed, **edit the homepage & callback URLs in your GitHub OAuth App to match your deployment URL**.

Alternatively, you can directly deploy it from Vercel and add everything as you go by clicking [here](https://vercel.com/templates/next.js/mongodb-starter). You can also find more documentation there, though I've tried to be as exhaustive as possible and have taken first-time Typescript users in mind.

## Installation

After installing dependencies (npm install), run the development server:

```bash
npm run dev
```

    or

```bash
npm start
```

The latter command presupposes you have a build already packaged. If not, type in:

```bash
npm run build
```

In order for you to run this on localhost (dev mode), you must add your MongoDB_URI on a local .env config file, as well as this line:

```bash
NEXTAUTH_URL=http://localhost:3000/api/auth
```

Refer to the package.json file to see all the available scripts you can run with git.

**NOTE FOR WINDOWS USERS**

You must install the following package to compile a build package on a Windows machine:

```bash
npm install -g win-node-env
```

## Vercel + MongoDB Integration

https://vercel.com/integrations/mongodbatlas

If you deploy this repo directly from Vercel, a database will be automatically created for you on MongoDB. There will be a database named, "test," and a collection named, "users."
You have to manually change this on the user.ts file that's located in lib/api/user.ts. You have to make this change regardless whether you used Vercel or not. Look for the following:

```bash
const collection = client.db('test').collection('users');
```

Just change "test" to whatever your database is called.

## Tech Stack

- [Next.js](https://nextjs.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [NextAuth.js](https://next-auth.js.org/)
- [MongoDB Atlas](https://www.mongodb.com/atlas/database)
- [Vercel](https://vercel.com/)
