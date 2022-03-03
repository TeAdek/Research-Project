# Research-Project
## A short summary of the video I used relating to my research topic
### Table Views
I followed *raywenderlich’s Table Views* tutorial where they used creating a **simple book library** as a way to learn general table view logic or method. I learnt about rows, cells, prototype cells and how to create table view on the interface builder. 

> Table views divide their delegation responsibilities in two method. The data source provides information about what to display, like how many rows, and what goes in each row. The delegate tells the tableview what to do when the user selects a row, or whether the user is allowed to edit a row, and other things like that.

The data source protocol requirement are of two methods.
- Method number one is number of rows in this section. 

- Method number two is cell for row at index path. This method is in charge of setting up the cells. This can be done using dequeueReusableCell method which enables the table view to reuses cells. 

```
func dequeueReusableCell(withIdentifier identifier: String) -> UITableViewCell?
```

This method takes two parameters, a string identifier and an index path. IndexPath parameter contains the number of the section and the row of the cell table view is interested in. It then gets a table view cell for this index path, based on the reuse identifier in Interface Builder.

```
override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int 

override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell 
```

I learnt a transition between two view controllers in your app’s storyboard file is called a segue. The starting point of a segue is the button, table row, or gesture recognizer that initiates the segue. The end point of a segue is the view controller you want to display. I made a custom UITableViewCell class and static table view because static table view filled with static cells is a great options for forms or setting screens. I made two sections by using numberOfSections function and update number of rows in section. To tell the table view that the data has been updated, I reload table view data using reloadData(). 

Diffable data source is the object you use to manage data and provide cells for a table view. I swapped our old school data source for a diffable data source. 
```
@MainActor class UITableViewDiffableDataSource<SectionIdentifierType, ItemIdentifierType> : NSObject where SectionIdentifierType : Hashable, ItemIdentifierType : Hashable
```
I use the diffable data source to add and remove rows from table view.
```
optional func tableView(_ tableView: UITableView, 
           canEditRowAt indexPath: IndexPath) -> Bool
```
I learnt how move rows in a table view. 
```
optional func tableView(_ tableView: UITableView, 
           canMoveRowAt indexPath: IndexPath) -> Bool

optional func tableView(_ tableView: UITableView, 
              moveRowAt sourceIndexPath: IndexPath, 
                     to destinationIndexPath: IndexPath)
```                   
It was a helpful tutorial on giving me a head start on what it entails when making an app that requires table view. 
But I still have much to learn on how to save data in iOS and how to use API