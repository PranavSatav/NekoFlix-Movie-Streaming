# NekoFlix-Movie-Streaming
NekoFlix, an awesome website to watch movies / series for free


This service works by displaying video files from third-party providers inside an intuitive and aesthetic user interface.

Features include:

- 🕑 Saving of your progress so you can come back to a video at any time!
- 🔖 Bookmarks to keep track of videos you would like to watch.
- 🎞️ Easy switching between seasons and episodes for a TV series; binge away!
- ✖️ Supports multiple types of content including movies, TV shows and Anime (coming soon™️)

## Goals of NekoFlix

- No ads
- No BS: just a search bar and a video player
- No responsibility on the hoster, no databases or api's hosted by us, just a static site

## How to Run

- https://nekoflixx.vercel.app - you can visit here #1

So you would like to self-host. This app is made of two parts:
 - The proxy
 - The client

## Hosting the proxy

The proxy is made as a Cloudflare worker. Cloudflare has a generous free plan, so you don't need to pay anything unless you get hundreds of users.

1. Create a Cloudflare account at [https://dash.cloudflare.com](https://dash.cloudflare.com).
2. Navigate to `Workers`.
3. If it asks you, choose a subdomain.
4. If it asks for a workers plan, press "Continue with free".
5. Create a new service with a name of your choice. Must be type `HTTP handler`.
6. On the service page, Click `Quick edit`.
7. Remove the template code in the quick edit window.
7. Download the `worker.js` file from the latest release of the proxy: [https://github.com/movie-web/simple-proxy/releases/latest](https://github.com/movie-web/simple-proxy/releases/latest).
8. Open the downloaded `worker.js` file in Notepad, Visual Studio Code or similar.
9. Copy the text contents of the `worker.js` file.
10. Paste the text contents into the edit screen of the Cloudflare service worker.
11. Click `Save and deploy` and confirm.

Your proxy is now hosted on Cloudflare. Note the url of your worker as you will need it later.

## Hosting the client

1. Download the file `.zip`.
2. Extract the zip file so you can edit the files.
3. Open `config.js` in Notepad, Visual Studio Code or similar.
4. Put your Cloudflare proxy URL in-between the double quotes of `VITE_CORS_PROXY_URL: ""`. Make sure to not have a slash at the end of your URL.

   Example (THIS IS AN EXAMPLE, IT WON'T WORK FOR YOU): `VITE_CORS_PROXY_URL: "https://test-proxy.test.workers.dev"`
5. Put your TMDB read access token inside the quotes of `VITE_TMDB_READ_API_KEY: ""`. You can generate it for free at [https://www.themoviedb.org/settings/api](https://www.themoviedb.org/settings/api).
6. Save the file

Your client has now been prepared, you can now host it with any static website hosting (Common ones include [GitHub Pages](https://pages.github.com/), [Netlify](https://www.netlify.com/) and [Vercel](https://vercel.com/) but any will work!).
It doesn't require PHP, it's just a standard static page.
  
<h1>Screenshots - Home Screen</h1>
<img src="https://i.imgur.com/cl3GdDC.png"/>
<h1>Search Menu</h1>
<img src="https://i.imgur.com/ofo0AZ6.png"/>
<h1>Scraping UI</h1>
<img src="https://i.imgur.com/8WzuYUU.png"/>
<h1>Player UI</h1>
<img src="https://i.imgur.com/Nk5O8ux.png"/>
