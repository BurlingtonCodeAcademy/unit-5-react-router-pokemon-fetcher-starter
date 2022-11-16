# React Router Pokemon Fetcher

## Objective

To understand how to use React Router to fetch a collection of Pokemon data as JSON which represents Pokemon.

## Learning

In this lab, we will use React.js to read JSON  which will contain Pokemon data within objects, and then use those objects to construct a React component for each Pokemon.

Topics:

- React components;
- React rendering collections;

## Achieving

Your work will result in:

- A parent component that displays a collection of child components containing Pokemon data.
- A function that returns components created from Pokemon objects.

## Procedure

### Add a route for the Pokemon Index page

- [ ] Add a route as an object with the properties:
  
```js
{
  path: urlPath<String>,
  elememnt: nameOfComponent<ReactComponent>, 
  loader: someLoaderFunction<Function>, // optional
  children: anArrayOfChildComponents<[ReactComponen]>, // optional
}
```

React-Router Documentation:

- Creating a Browser Router
  - <https://reactrouter.com/en/main/routers/create-browser-router>

### Create an request for Pokemon data from the Index route of the API

- Base Route: `https://pokeapi.co/api/v2/`
- Index of Pokemon: `/pokemon/`
  - List of Pokemon, defaults to 20, including their name, and the URL for the details of the Pokemon

- [ ] Initialize your data request using either `useEffect` or the default React Router `loader()` function exported by a component for a given component.

- [ ] Receive the data as a response from your request, and then inject that data into your component, and use it to render the initial list of Pokemon

React-Router Documentation:

- Setting the Loader Property on Route
  - <https://reactrouter.com/en/main/route/loader>
- Using the Loader Data
  - <https://reactrouter.com/en/main/hooks/useloader-data>

```js
{
  count: 1154,
  next: "https://pokeapi.co/api/v2/pokemon/?offset=20&limit=20",
  previous: null,
  results: [
    {
    name: "bulbasaur", // Pokemon name
    url: "https://pokeapi.co/api/v2/pokemon/1/" // Pokemon URL
    },
    {
    name: "ivysaur", // Pokemon name
    url: "https://pokeapi.co/api/v2/pokemon/2/" // Pokemon URL
    },
  ...
}
```

### Create a route for the Pokemon details page

Create your router within the `createBrowserRouter` for a detail page of a Pokemon.

- [ ] Add a route as an object with the properties:
  
```js
{
  path: urlPath<String>,
  elememnt: nameOfComponent<ReactComponent>, 
  loader: someLoaderFunction<Function>, // optional
  children: anArrayOfChildComponents<[ReactComponen]>, // optional
}
```

- [ ] Add a path param to the route, using the `:paramName` syntax within the path property of the route.

React-Router Documentation:

- Using a Router Parameter
  - <https://reactrouter.com/en/main/hooks/use-params>

### Create an request for Pokemon data from the detail route of the API

- Details of Pokemon: `/pokemon/<someId>`
  - Pokemon details as a single object

- [ ] Initialize your data request using either `useEffect` or the default React Router `loader()` function exported by a component for a given component.

- [ ] Receive the individual Pokemon data as a response from your request, and then inject that data into your component, and use it to render the initial list of Pokemon

React-Router Documentation:

- Setting the Loader Property on Route
  - <https://reactrouter.com/en/main/route/loader>
- Using the Loader Data
  - <https://reactrouter.com/en/main/hooks/useloader-data>

```js
{
  abilities: [
  {
    ability: {
    name: "overgrow",
    url: "https://pokeapi.co/api/v2/ability/65/"
    },
    is_hidden: false,
    slot: 1
    },
    {
    ability: {
    name: "chlorophyll",
    url: "https://pokeapi.co/api/v2/ability/34/"
    },
    is_hidden: true,
    slot: 3
    }
  ],
  base_experience: 64,
  forms: [
    {
    name: "bulbasaur",
    url: "https://pokeapi.co/api/v2/pokemon-form/1/"
    }
  ],
  ...
```

### Create a `<Link>` component to create a route from the Index page to a detail page

- [ ] For each Pokemon in the index, create a `<Link>`, apply correct path value within the `to={}` prop, so that the data is retrieved for that Pokemon as a secondary request.
- [ ] Use the data from the initial request of the Pokemon index in the subsequent detail request.

React-Router Documentation:

- Creating a Link Component
  - <https://reactrouter.com/en/main/components/link>

### Add a Nav Bar to the Layout of the Application

Use a component as a layout parent, and nest the children components within it, so that a navigation bar is displayed on every child page.

- [ ] Add a route for the base `/` which nests the children within it.
- [ ] Use the component as a layout, by adding an `<Output />` to the base component, so that children can be rendered when their paths match.
- [ ] Update the child `{ path }` property so that when the child is visited, only it is shown, and not any other children.

React-Router Documentation:

- Using an Outlet Component within a Layout
  - <https://reactrouter.com/en/main/components/outlet>

## Going Further

- Can we get information about multiple Pokemon forms onto the same page, such that the evolution of a Pokemon can be listed together on one route?
- How should you style the Pokemon page?
- Can you create a way to search for Pokemon?

## Helpful Resources

The following links are documentation pages on the React-Router project that will prove helpful in your project work.

- Creating a Browser Router
  - <https://reactrouter.com/en/main/routers/create-browser-router>
- Setting the Loader Property on Route
  - <https://reactrouter.com/en/main/route/loader>
- Using the Loader Data
  - <https://reactrouter.com/en/main/hooks/useloader-data>
- Creating a Link Component
  - <https://reactrouter.com/en/main/components/link>
- Using a Router Parameter
  - <https://reactrouter.com/en/main/hooks/use-params>
- Using an Outlet Component within a Layout
  - <https://reactrouter.com/en/main/components/outlet>
