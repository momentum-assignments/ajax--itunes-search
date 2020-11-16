# iTunes Search

## Directions

For this app, we will request data from the iTunes API.

You'll use artist data from the API to display song titles, and then allow the user to select and play song previews. Here is an idea of what the [end result](musicapp.jpg) could look like, though you can customize the design however you like.

Here are the steps you'll need to take in order to complete this project.

1. Build a form that has an `<input>` where a user can fill in a band or artist.
2. When the user types in a band or artist and presses the submit button (or presses Enter), you will make the search request to the API.
3. When the API returns a response, use the results to display a listing of songs related to the search term.
4. When a user clicks a song in your listing, the song should play in an `<audio>` tag that you've also added to the page (see [the mockup](musicapp.jpg)).

### Hints & Tips

There will be some new concepts you'll need to work through on this project, so feel free to ask for assistance along the way.

- [iTunes API documents](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/Searching.html#//apple_ref/doc/uid/TP40017632-CH5-SW1)
  - Read through the documentation before getting started. Everything you'll need to know is in there.
  - Use Insomnia to make requests to the API to test out the URLs you will need to construct and see data that is returned.
- Playing a song preview
  - You'll need to research the `<audio>` tag for this part - [docs here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
  - **Hint**: _You'll need to dynamically change the `src` value_

**NOTE**: The iTunes API can be a little flaky when it comes to returning CORS headers. These headers are necessary for Ajax to work correctly. If you have any problems, you can use a proxy we've set up. Replace `https://itunes.apple.com/` in the API URL with `https://itunes-api-proxy.glitch.me/`.

One hard part will be getting the song to play. Since you will be dynamically generating the HTML for your results, adding an event listener to each result can be tricky. One way to make this easier is to put your `click` event listener on a parent node (like a `div` around the entire results section) and then get the item that the user click by getting the `event.target` in your event listener callback. This is called "event delegation" and here is a comprehensive [article on the technique](https://davidwalsh.name/event-delegate).

### Bonus

Add a radio button to switch the search between artist, song title, or album title.
