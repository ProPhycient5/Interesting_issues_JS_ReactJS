- #### Below is the code (in react) for logic of search engine type function that uses native JS method like `filter()`, `toLowerCase()` and `includes()`.  


```
import { useState } from "react";

export default function App() {
  const data = [
    {
      id: 1,
      name: "John Smith"
    },
    {
      id: 2,
      name: "Jane Smith"
    },
    {
      id: 3,
      name: "Joe Shmoe"
    },
    {
      id: 4,
      name: "Jacob"
    }
  ];
  const [filteredData, setFilteredData] = useState(data);

  *Below function is the logic for searh bar from data structure*
  const searchFn = (e) => {
    let processedData = data.filter((item) =>
      item.name.toLowerCase().includes(e.target.value.toLowerCase())
    );
    setFilteredData(processedData);
  };

  return (
    <div className="App">
      <h1>Search bar</h1>
      <input type="text" placeholder="Search" onKeyUp={searchFn} />
      <ul>
        {filteredData.map((user) => (
          <li key={user.id}>{user.name}</li>
        ))}
      </ul>
    </div>
  );
}
```
