## useModal
**modals.ts**

        export type typeModalOpen = "openImage" | "close";

**useModal.tsx**
        import { useState } from "react";
        import { typeModalOpen } from "src/models/modals";
        
        export const useModal = () => {
          const [isOpenModal, setIsOpenModal] = useState<typeModalOpen>("close");
        
          const closeModal = () => {
            setIsOpenModal("close");
          };
        
          return {
            isOpenModal,
            setIsOpenModal,
            closeModal,
          };
        };

        
**PortalModal.tsx**

        import { ReactNode } from "react";
        import { createPortal } from "react-dom";
        import { typeModalOpen } from "src/models";
        
        createPortal;
        
        interface ModalProps {
          close: () => void;
          isOpen: typeModalOpen;
          typeModal: typeModalOpen;
          className: string;
          children: ReactNode;
        }
        
        const PortalModal = ({
          close,
          isOpen,
          className,
          children,
          typeModal,
        }: ModalProps) => {
          return createPortal(
            <>
              <div
                onClick={close}
                className={`${
                  isOpen === typeModal ? "" : "hidden"
                } cursor-pointer mx-auto overflow-y-auto overflow-x-hidden fixed top-0 right-0 left-0 z-[102] justify-center items-center w-full md:inset-0 h-[calc(100%-1rem)] max-h-full bg-gray-900 opacity-90`}
              ></div>
              <div
                id="productModal"
                className={`${
                  isOpen === typeModal ? "flex" : "hidden"
                } mx-auto overflow-y-auto overflow-x-hidden fixed z-[103] justify-center items-center w-full md:inset-0 h-[calc(100%-1rem)] max-h-full opacity-100`}
              >
                <div
                  className={`${className} relative shadow rounded-lg p-8 w-full max-h-full z-[104]`}
                >
                  <div className="flex justify-between items-center rounded-t border-b  dark:border-gray-600">
                    <button
                      type="button"
                      onClick={close}
                      className="w-8 h-8 p-2 flex justify-center items-center bg-white rounded-sm right-10 top-10  text-2xl absolute cursor-pointer gap-4 z-[105] text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 ml-auto dark:hover:bg-gray-600 dark:hover:text-white"
                    >
                      X
                    </button>
                  </div>
                  {children}
                </div>
              </div>
            </>,
            document.body
          );
        };
        
        export default PortalModal;
        
**Example.tsx**
 
         const { setIsOpenModal, closeModal, isOpenModal } = useModal();
        
          return (
              <PortalModal
                close={closeModal}
                typeModal="openImage"
                isOpen={isOpenModal}
                className={"bg-slate-200 max-w-xl"}
              >
              ...
              </PortalModal>
          )
          

## useDebounce
    export function useDebounce<T>(value: T, delay = 500): T {
      const [debouncedValue, setDebouncedValue] = useState(value);
    
      useEffect(() => {
        const timerId = setTimeout(() => setDebouncedValue(value), delay);
    
        return () => clearTimeout(timerId);
      }, [value, delay]);
    
      return debouncedValue;
    }

## useLocalStorage
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

## useContext
    export function useBookmarksContext() {
      const context = useContext(BookmarksContext);
      if (!context) {
        throw new Error(
          "useBookmarksContext must be used within a BookmarksContextProvider"
        );
      }
      return context;
    }



## useFetch

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


