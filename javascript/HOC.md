## Higher-Order Component



### Services

    import WithSearch from './WithSearch';
    import TodoList from './TodoList';
    
    const Services = () => {
      const Services = [
        { id: 0, title: 'servicio 1', completed: true },
        { id: 1, title: 'servicio 2', completed: false },
        { id: 2, title: 'servicio 3', completed: false },
      ];
    
      const ToDoListWithSearch = WithSearch({ Component: TodoList, dataSet: Services });
    
      return ToDoListWithSearch;
    };
    
    export default Services;


### Tasks
    const Tasks = () => {
      const tasks = [
        { id: 0, title: 'tarea 1', completed: false },
        { id: 1, title: 'tarea 2', completed: true },
        { id: 2, title: 'tarea 3', completed: true },
      ];
    
      const ToDoListWithSearch = WithSearch({ Component: TodoList, dataSet: tasks });
    
      return ToDoListWithSearch;
    };
    
    export default Tasks;
