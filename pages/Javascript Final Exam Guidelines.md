- Weighted 50/50 MC and written
- # What to study
	- ## MQ
		- Majority is Express
		- Remaining mostly previous mid term questions
		- 1 question about streams
			- Types of streams
			- What stream does PNGJS use?
		- 1 question about DB
			- How does express communicate with a database?
				- Install database driver
		- ~2 sync/async questions
	- ## Written
		- Designed to be much easier than midterm
		- Read 2 (JSON) files and write functions to answer some questions
			- One file about soccer players
			- One file about soccer games
			- ex. Who is the tallest player?
		- 4 questions
			- first 3 only use soccer player data
			- 4th question about both files
		- Recommended set up for 100%
			- Need to read both files simultainiously
			- ```Javascript
			  // This is the recommended set up for the written portion.
			  // If you don't remove these comments then...
			  
			  const fs = require("fs/promises");
			  
			  const main = async () => {
			    // this reads both files in parallel
			    // faster that reading individually
			    const [content1, content2] = await Promise.all([
			      fs.readFile('file1.json', 'utf-8'), 
			      fs.readFile('file2.json', 'utf-8')
			    ]); 
			  
			    // these are functions
			    question1(content1);
			    question2(content1);
			    question3(content1);
			    question4(content2);
			  
			  }
			  ```
		-