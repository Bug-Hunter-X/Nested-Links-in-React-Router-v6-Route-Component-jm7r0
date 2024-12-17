# React Router v6 Nested Links Issue

This repository demonstrates a bug in React Router v6 where nested Link components within a Route element behave unexpectedly when navigating between routes.  The issue causes the nested links to not properly update their active state, leading to an inaccurate display. 

## Bug Description:
Nested Link components within a Route component do not update their active state correctly when navigating to a different route, only refreshing on explicit page reload.  This issue does not appear to manifest when links are not nested within a Route component.  This issue seems to cause a failure in re-rendering of the parent component when the navigation occurs.

## Reproduction Steps:
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Navigate between the Home and About pages. Observe that the link's active state doesn't update immediately, and the page display is not refreshed until a hard refresh or direct browser navigation is performed. 

## Solution:
The solution involves using the `useLocation` hook to force a re-render of the parent component whenever the URL changes. This ensures that the nested links' active states are always updated correctly, fixing the unexpected behavior.