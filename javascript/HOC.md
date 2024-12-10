## Higher-Order Component



### Services (similar 1)

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


### Tasks (similar 2)

    import WithSearch from './WithSearch';
    import TodoList from './TodoList';
    
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


### ToDoItem

    const ToDoItem = ({ title, completed }: { title: string; completed: boolean }) => {
      return (
        <div>
          <input type='checkbox' defaultChecked={completed} className='mr-2' />
          {title}
        </div>
      );
    };
    
    export default ToDoItem;

### TodoList

    const TodoList = ({ query, dataSet }: { query: string; dataSet: dataSet[] }) => {
      const items = filterItems(query, dataSet);
      return (
        <div>
          {items.map((product, index) => (
            <ToDoItem key={index} title={product.title} completed={product.completed} />
          ))}
        </div>
      );
    };
    
    export default TodoList;


### WithSearch

    const WithSearch = ({ Component, dataSet }: { Component: any; dataSet: any }) => {
      const [query, setQuery] = useState('');
    
      const handleChange = (e: any) => {
        setQuery(e.target.value.toLowerCase()); //all logic
      };
      return (
        <>
          <input onChange={handleChange} type='text' className='border-2 border-black ' />
          <Component query={query} dataSet={dataSet} />
        </>
      );
    };
    
    export default WithSearch;
