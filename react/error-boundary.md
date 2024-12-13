    // Importamos los componentes necesarios de React
    import { Component, ErrorInfo, ReactNode } from "react";
    
    // Definimos la interfaz del estado del componente ErrorBoundary
    interface ErrorBoundaryState {
      hasError: boolean; // Indica si se ha producido un error
    }
    
    // Definimos la interfaz de las propiedades que puede recibir el componente ErrorBoundary
    interface ErrorBoundaryProps {
      children: ReactNode; // Los componentes hijos que serán renderizados por el ErrorBoundary
    }
    
    // Creamos la clase ErrorBoundary que extiende de la clase Component de React
    class ErrorBoundary extends Component<ErrorBoundaryProps, ErrorBoundaryState> {
      // Constructor para inicializar el estado del componente
      constructor(props: ErrorBoundaryProps) {
        super(props);
        this.state = { hasError: false }; // Inicializamos el estado con hasError en false
      }
    
      // Método estático que se llama cuando se produce un error en alguno de los componentes hijos
      static getDerivedStateFromError(error: Error): ErrorBoundaryState {
        console.log("Derived Error", error); // Registramos el error en la consola
        return { hasError: true }; // Actualizamos el estado para indicar que se ha producido un error
      }
    
      // Método que se llama después de getDerivedStateFromError para obtener más información sobre el error
      componentDidCatch(error: Error, errorInfo: ErrorInfo): void {
        console.log("Error:", error); // Registramos el error en la consola
        console.log("Error Info:", errorInfo); // Registramos información adicional sobre el error en la consola
      }
    
      // Método render que determina qué se renderiza en pantalla
      render() {
        if (this.state.hasError) {
          // Si se ha producido un error, renderizamos un mensaje de error
          return <h1>Oops! I did it again ;)</h1>;
        } else {
          // Si no se ha producido un error, renderizamos los componentes hijos originales
          return this.props.children;
        }
      }
    }
    
    // Exportamos el componente ErrorBoundary para poder usarlo en otras partes de la aplicación
    export default ErrorBoundary;
