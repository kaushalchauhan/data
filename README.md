### fetch constant data from github raw,
this is just a cool stuff, I can also use this just using a constant file but to learn thing something new, to fetch data from github raw and this is bcz im trying this.

``` 
const fetchData = async () => {
  try {
    const response = await fetch(
      'https://raw.githubusercontent.com/username/repository/branch/path/to/your/file.ts'
    );

    if (!response.ok) {
      throw new Error(`Failed to fetch data: ${response.status} ${response.statusText}`);
    }

    const data = await response.text();

    // Use eval or Function to execute the code and retrieve the jobs array
    const executeCode = new Function('return ' + data);
    const result = executeCode();

    // Now 'result.jobs' contains the jobs array
    console.log(result.jobs);
  } catch (error) {
    console.error(error);
  }
};

fetchData();
