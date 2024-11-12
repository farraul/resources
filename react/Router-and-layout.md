### RouterProvider.tsx


    import { RouterProvider as Provider } from "react-router-dom";
    import { routesConfig } from "./routesConfig";
    import { Spinner } from "src/components";
    import { Suspense } from "react";
    
    const RouterProvider = () => {
      return (
        <Suspense fallback={<Spinner />}>
          <Provider router={routesConfig} />
        </Suspense>
      );
    };
    
    export default RouterProvider;

### routesConfig.tsx

    import { Suspense, lazy } from "react";
    import { createBrowserRouter } from "react-router-dom";
    import { Spinner } from "src/components";
    import { Layout } from "src/layout/Layout";
    
    const HomePage = lazy(() => import("src/pages/Home/HomePage"));
    const ErrorPage = lazy(() => import("src/pages/Error/ErrorPage"));
    
    export const routesConfig = createBrowserRouter([
      {
        path: "/",
        element: <Layout />,
        children: [
          {
            index: true,
            element: (
              <Suspense fallback={<Spinner />}>
                <HomePage />
              </Suspense>
            ),
          },
          {
            path: "*",
            element: <ErrorPage />,
          },
        ],
      },
    ]);


    
### Layout.tsx


    import { Outlet } from "react-router-dom";
    import { Footer, Header } from "src/components";
    
    export const Layout = () => {
      return (
        <>
          <Header />
          <main>
            <Outlet />
          </main>
          <Footer />
        </>
      );
    };
