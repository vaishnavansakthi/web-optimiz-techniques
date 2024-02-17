# web-optimiz-techniques
Collecting more information about web security and optimization techniques.
This is test branch code.


# React App Optimization
# Make Use of React.Fragment to Avoid Adding Extra Nodes to the DOM

React fragments serve as a cleaner alternative to using unnecessary division in the code. Since the fragments don't add any new elements to the DOM, their children will simply render without the need for a wrapper DOM node.

There are instances in React where you'll need to render many elements or deliver a collection of related objects. Are you curious arebout what we're referring to? Let's examine the illustration.

```
    function App() {
        return(
            <div>
                <h1>Welcome React! </h1>
                <h1>Welcome React Again! </h1>
            </div>
        );
    }

```

An error message reading "Adjacent JSX elements must be wrapped in an enclosed tag" will be displayed if you use this code. As a result, you will need to include both the elements inside the parent div.

Even if it will fix the problem in the best way possible, you should be aware that there is a risk involved. In this case, the DOM gains an additional node. A problem arises in these situations when a child component is encased within the parent component.

One of the best ways to solve this problem is that you consider using React Fragment which will not add an additional node to the DOM.

```
    function App() {
        return (
            <React.Fragment>
                <td> Welcome React! </td>
                <td> Welcome React Again! </td>
            <React.Fragment>
        );
    }

```    
# Make Use of React.Suspense and React.Lazy for Lazy Loading Components

Now, loading every component, even if the end users do not need it, may impact the overall performance of your React application and the user experience.

**Load component without Lazy Load**

```
import React from 'react';
import GalleryComponent from './GalleryComponent'

const HomeComponent = () => (
    <div>
        <GalleryComponent />
    </div>
)
```

**Load component with Lazy Load**

```
import React, { lazy } from 'react';
const GalleryComponent = lazy(() => import('./GalleryComponent'));

const HomeComponent = () => (
    <div>
        <GalleryComponent />
    </div>
)
```
By now, you must have a clarity that the addition of Lazy Load is simple and extremely worth it.

Now let us walk you through the lazy Load and Suspense Combination.

Knowing how Lazy Load functions and how it may improve the user experience and performance of React applications, you must be wondering why we also need Lazy Suspense.

To understand the same, let us get started by considering and looking at an example, one like we have used before.

This time, let us consider that <GalleryComponent /> contains one of the problems like: API requests that take a few seconds to return a result, weaker devices, bad network connection, or large JavaScript payload.

```
import React, { lazy } from 'react';

/*
- GalleryComponent contain API request / large JavaScript payload.
*/
const GalleryComponent = lazy(() => import('./GalleryComponent'));

const HomeComponent = () => (
    <div>
        <GalleryComponent />
    </div>
)
```

It goes without saying that this command is poor for the user experience because there is a risk that the user may see a blank area for a few seconds while waiting for the <GalleryComponent/> to respond. This is where React Suspense enters the picture.

React Suspense works in the best possible ways to display components to the users that depict the users that the component is loading at the moment, so that the users see that message while there’s a delay in loading. Isn't that great? It is, right!

```
import React, { lazy, Suspense } from 'react';

const GalleryComponent = lazy(() => import('./GalleryComponent'));

const renderLoader = () => <p>Loading...</p>;

const DetailsComponent = () => (
    <Suspense fallback={renderLoader()}>
        <GalleryComponent />
    </Suspense>
)
```

The suspense tends to receive a fallback component that will be displayed to the users while the loading delay. With this, the users will see “loading...” prompt while the <GalleryComponent />, is load.

## Use Production Build

Make sure to test any performance issues you may be seeing with your React apps using the production build's minified version.

React comes with a number of useful warnings by default. These cautions are quite important, especially when it comes to development. It's crucial that you utilize the production version, especially when deploying the project, as they have a tendency to make React bulkier and slower.

Well, if you are unsure about the setup of your build process, you can make the most out of React Developer Tools for Chrome to conduct a check. Moreover, when you visit the site with React in production mode, remember, the icon will have a dark background.

**React Developer Tools**
{https://radixweb.com/blog/top-react-developer-tools}

Also, if you visit the site when React is in development mode, the icon will have a red background.

When it comes to working on your app, ensure that you make use of development mode. On the other hand, when releasing it to the users, you should use a production model.

*Note – Make sure to update React from development files to production-ready ones if you use React via CDN.*

## Make Use of React.memo for Component Memoization

Memorization is a technique for speeding up computer programs by caching the outcomes of pricey function calls and returning them when the same inputs are encountered again.

Now that you have an understanding of what is memoization, let us understand and look at how does it really works.

With the assistance of this method, a certain function is produced, and the result is saved in memory. When a function with the same parameter is called in the future, it provides the result-saving bandwidth.

Let's dive more into the same.

Functions are functional components in React, whereas arguments are props.

To make things clearer for you, here is an illustration.

```
import React from ‘react’;

Const MyComponent = React.memo(props => {/* render only if the props changed */});

```

# Understand the Handling of ‘THIS’

In case you are someone who’d wish to employ functional components, then one thing you need to understand is that it does not require THIS binding.

#  Make Use of Function in "SetState"

In SetState, it is recommended to use a function rather than an object. The same is recommended because state changes do not happen immediately, contrary to what the React documentation assumes.

Thus, instead of this:

```
this.setState({correctData: !this.state.correctData});
```

Use this:

```
this.setState((prevState, props) => {
    return {correctData: !prevState.correctData});
}
```
This function will receive the previous state as its first argument, and the props at the time the update is applied as the second argument.




