# Magine front-end code test

## The goal
Create a working single page application containing following technologies Webpack, Babel, React, Jsx, Redux, Graphql, Html5 routing and Shaka-Player. The app should contain two views. The primary view (`/`) should be a list of links to all the movies. The secondary view (`/movie/:movieId`) should contain a player with player controls (play/pause/progressbar). You can add some styling if you want to show off your css skills!

## Steps
- Setup a simple webpack configuration with babel.
- Use the React router of your choice. Define two endpoint `/` and `/movie/:movieId`.
- The view `/`: should contain a list of movie links with their name as content. The data should be fetched from the graphql server provided by this repository and be stored in Redux. Only request the data you need. In this case `id` and `name`. Clicking the link should navigate to the secondary view using "pushState" (no unloading of the page).
- The view `/movie/:movieId`: should contain a player and player controls.

## Conditions
- No boilerplate allowed.
- Write good readable/simple code.
- Components should be stateless. Store all states in either Redux or `history.state`. If you need to store state within the component then add a comment why you need it.
- The `<video controls />` isn't allowed. You need to create two React components `<Player />` and `<PlayerControls />`.
- The player should have controlled input like `<input value={value} onChange={handleValue} />` but `<Player currentTime={currentTime} onTimeUpdate={handleTimeUpdate} />`. https://reactjs.org/docs/forms.html#controlled-components

## The Player interface
```js
// Should use the Shaka player
// https://github.com/google/shaka-player
class Player extends Component {
  static propTypes = {
    src: PropTypes.string,
    currentTime: PropTypes.number,
    onLoadedMetaData: PropTypes.func, // used to get duration
    onTimeUpdate: PropTypes.func, // used to get current time
    play: PropTypes.bool,
  };
}
```
