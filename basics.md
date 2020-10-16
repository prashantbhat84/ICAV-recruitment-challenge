1. The N+1 problem is a peculiar probelm of joins. Here is how it works . Let us consider the example of Author and Books where Author and Books are 2 different collections in MongoDB. In the Books collection the author id is stored which links the book to the author. Let say for a individual author we need the list of all Books .Assuming the author name is sent from the front end to the backend server in that situation we need to get all author details from the author table. This is one DB hit. This will give us the id and then we need to get allthe author from the books collection by that id. for every book we need to check in db weather it belongs to that author. SO there will be N hits to the Books collection. This is a N+1 problem.

To Solve this problem if we are using graphql we can use the dataloaders concept to get all the records from both tables and filter accordingly. But if we are using Node.js then we need to get the records and then filter the tables. So instead of N+1 hits we will have only 2 hits to the DB.

2. I will stop writing Unit tests in the following situations
   a. Code is trivial
   b.Code needs to interact with other systems in which case Integration tests are required
   c.If the result of the test is difficult to quantify
   d.If the magnitude of writing test is more difficult than writing of code.

3. Monorepos need to be used because it creates a single source of truth. In simple terms we can create a repo and branches like development/test etc... This will ensure that all team members are commitingto the same branch and collaboration is easy in terms of remote development

4.
