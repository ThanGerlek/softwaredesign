
#  React Hooks and State

## React Hooks

- React hooks are functions that give functional components access to built-in React features (state management, route navigation, etc.).
- Hook functions have names starting with the word `use`.
- Hooks can only be called by components or other hooks.

## Commonly-Used Hooks

- Executing non-rendering logic
    - [useEffect](./useEffect.md)
- Access current route (URL)
    - [useLocation](./useLocation.md)
    - [useParams](./useParams.md)
- Change current route
    - [useNavigate](./useNavigate.md)

## State Hooks

- Persisting values across re-renders
    - [useState](./useState.md)
    - useRef
        - [Persisting values](./useRef-non-dom.md)
        - [Accessing DOM elements](./useRef-dom.md)
- Avoiding unnecessary computation
    - [useMemo](./useMemo.md)
    - [useCallback](./useCallback.md)
- Sharing state across components
    - [useContext](./useContext.md)


## Custom Hooks

Custom hooks can be written to:
1. Provide app-specific functionality
1. Remove/avoid code duplication in functional components

Custom hook from Tweeter project:

```
import { useContext } from "react";
import { ToastActionsContext } from "./ToastContexts";
import { ToastType } from "./Toast";

export type MessageActions = {
    displayInfoMessage: (message: string, duration: number, bootstrapClasses?: string) => string,
    displayErrorMessage: (message: string, bootstrapClasses?: string) => string,
    deleteMessage: (messageId: string) => void,
    deleteAllMessages: () => void,
};

export const useMessageActions = () => {
    const { displayToast, deleteToast, deleteAllToasts } = useContext(ToastActionsContext);

    const displayInfoMessage = (message: string, duration: number, bootstrapClasses?: string): string => {
        const toast = displayToast(ToastType.Info, message, duration, undefined, bootstrapClasses);
        return toast;
    };

    const displayErrorMessage = (message: string, bootstrapClasses?: string): string => {
        const toast = displayToast(ToastType.Error, message, 0, undefined, bootstrapClasses);
        return toast;
    };

    return {
        displayInfoMessage,
        displayErrorMessage,
        deleteMessage: deleteToast,
        deleteAllMessages: deleteAllToasts
    };
}
```
