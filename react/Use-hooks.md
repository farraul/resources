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
**File1**

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

**File2**

      const [bookmarkedIds, setBookmarkedIds] = useLocalStorage<number[]>(
        "bookmarkedIds",
        []
      );

### useContext
    export function useBookmarksContext() {
      const context = useContext(BookmarksContext);
      if (!context) {
        throw new Error(
          "useBookmarksContext must be used within a BookmarksContextProvider"
        );
      }
      return context;
    }



### useFetch

        export const useFetch = (url: string) => {
          const [data, setData] = useState<any>();
          const [loading, setLoading] = useState<boolean>(true);
          const [error, setError] = useState<string>('');
          const [controller, setController] = useState<AbortController>();
        
          useEffect(() => {
            const abortController = new AbortController();
            setController(abortController);
        
            fetch(url, { signal: abortController.signal })
              .then((response) => response.json())
              .then((json) => setData(json))
              .catch((error) => {
                if (error.name === 'AbortError') {
                console.log("Requerst cancelled")
                } else {
                  setError(error);
                }
              })
              .finally(() => setLoading(false));
        
            return () => abortController.abort();
          }, []);
        
          const handleCancelRequest = () => {
            if (controller) {
              controller.abort();
              setError('Cancelled Request');
            }
          };
        
          return { data, loading, error, handleCancelRequest };
        };


