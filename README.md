## useHooks

### useDebounce
    export function useDebounce<T>(value: T, delay = 500): T {
      const [debouncedValue, setDebouncedValue] = useState(value);
    
      useEffect(() => {
        const timerId = setTimeout(() => setDebouncedValue(value), delay);
    
        return () => clearTimeout(timerId);
      }, [value, delay]);
    
      return debouncedValue;
    }

### useLocalStorage
```javascript
export function useLocalStorage<T>(
  key: string,
  initialValue: T
): [T, React.Dispatch<React.SetStateAction<T>>] {
  const [value, setValue] = useState(() =>
    JSON.parse(localStorage.getItem(key) || JSON.stringify(initialValue))
  );

  useEffect(() => {
    localStorage.setItem(key, JSON.stringify(value));
  }, [value, key]);

  return [value, setValue] as const;
}

```
### useContextuseContext
    export function useBookmarksContext() {
      const context = useContext(BookmarksContext);
      if (!context) {
        throw new Error(
          "useBookmarksContext must be used within a BookmarksContextProvider"
        );
      }
      return context;
    }
    
## Utils

### handleError
    import toast from "react-hot-toast";
    export const handleError = (error: unknown) => {
      let message;
    
      if (error instanceof Error) {
        message = error.message;
      } else if (typeof error === "string") {
        message = error;
      } else {
        message = "An error occurred.";
      }
    
      toast.error(message);
    };



