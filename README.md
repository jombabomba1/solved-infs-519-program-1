Download Link: https://assignmentchef.com/product/solved-infs-519-program-1
<br>
Your program will create a class to implement the Table abstract data type and then use this class to implement a simple address book.

Table i s an ADT which stores pairs of values: a <em>key </em>and a <em>value</em>. The key must be unique and is used to identify the pair. There are three operations:

<ul>

 <li>value lookup(key) searches the table for a pair with the given key and returns the corresponding value.</li>

 <li>boolean insert(key, value) stores the key/value pair in the table.</li>

 <li>boolean delete(key) removes the key/value pair with given key from the</li>

</ul>

Public methods for your Table class are described below.

The address book will store names (used as keys) and addresses that are associated with the names. The program will present the user a menu with a choice of operations: <em>add </em>a name (and address), <em>look up </em>a name (displaying the associated address), <em>update </em>the address for a name, <em>delete </em>an entry, <em>display all </em>entries (including the total # of entries), and <em>quit</em>.

If the user chooses <em>add </em>the program prompts for a name. If the name already exists in the address book a message is displayed to that effect and no change is made. Otherwise the program asks for an associated address and the new entry is made. If the user chooses <em>look up </em>he or she is asked for a name. The program will look up the entry for that name and display the associated address. If the user

chooses <em>update, </em>he or she is asked for a name. The name is looked up and the address displayed. The user is then prompted for a new address which is accepted and stored in place of the old address. For <em>delete </em>the user is asked for a name and the entry for that name is removed from the address book. In any of these cases (other than insert) if the name given by the user is not found, an appropriate message is displayed. If the user selects <em>display all, </em>all of the names and addresses in the address book are displayed (the order is not important). The program continues displaying the menu and taking commands until the user chooses <em>quit</em>.

If the user enters a selection which is not in the menu, the menu will be displayed again and the user is prompted again for a command. The names and addresses can be any strings — your program need not check that they make any sense.




A sample run of the program may look like:

Add a name (n)

Look up a name (l) Update address (u) Delete an entry (d) Display all entries (a) Quit (q)

-&gt; n

Name: Genghis Khan

Address: Khentii Aimag, Mongolia

Add a name (n)

Look up a name (l) Update address (u) Delete an entry (d) Display all entries (a) Quit (q)

-&gt; n

Name: Rasputin

Address: St. Petersburg, Russia

Add a name (n)

Look up a name (l) Update address (u) Delete an entry (d) Display all entries (a) Quit (q)

-&gt; n

Name: Helen Mirren Address: London, England

Add a name (n)

Look up a name (l) Update address (u) Delete an entry (d) Display all entries (a) Quit (q)

-&gt; l

Name: Rasputin




Address is St. Petersburg, Russia

Add a name (n)

Look up a name (l) Update address (u) Delete an entry (d) Display all entries (a) Quit (q)

-&gt; u

Name: Rutherford B. Hayes Rutherford B. Hayes is not in the book

Add a name (n)

Look up a name (l) Update address (u) Delete an entry (d) Display all entries (a) Quit (q)

-&gt; u

Name: Helen Mirren

Old address is London, England New address: Hollywood, California

Add a name (n)

Look up a name (l) Update address (u) Delete an entry (d) Display all entries (a) Quit (q)

-&gt; d

Name to delete: Rasputin




Add a name (n)

Look up a name (l) Update address (u) Delete an entry (d) Display all entries (a) Quit (q)

-&gt; a

Total number of entries: 2

Name: Helen M irren

Address: Hollywood, California

Name: Genghis Khan

Address: Khentii Aimag, Mongolia

Add a name (n)

Look up a name (l) Update address (u) Delete an entry (d) Display all entries (a) Quit (q)

-&gt; q

<strong>Internals</strong>

You will write (among other classes) a class Table which will store entries which are (key/value) pairs of Strings. You will need to write a Node class which will have (as private fields) a key String (used to identify the entry) and a value String (used to store some data associated with the key) and a next pointer used for

linking. Table will have public methods:

<ul>

 <li>public boolean insert(String key, String value)</li>

</ul>

Inserts a new entry to the table. If an entry already exists with the given key value make no insertion but return false.

<ul>

 <li>public String lookUp(String key)</li>

</ul>

Looks up the entry with the given key and returns the associated value. If no entry is found null is returned.

<ul>

 <li>public boolean delete(String key)</li>

</ul>

Deletes the entry with the given key. If no entry is found returns false.

<ul>

 <li>public boolean update(String key, String newValue)</li>

</ul>

Replaces the old value associated with the given key with the newValue string.

<ul>

 <li>public boolean markToStart()</li>

</ul>

Sets the <em>mark </em>(see below) to the first item in the table. Returns false if the table is empty.




<ul>

 <li>public boolean advanceMark()</li>

</ul>

Moves the mark to the next item in the table. If there is no next item (e.g. at the end of the list) returns false.

<ul>

 <li>public String keyAtMark()</li>

</ul>

Returns the key stored in the item at the current mark.

<ul>

 <li>public String valueAtMark()</li>

</ul>

Returns the value stored in the item at the current mark.

<ul>

 <li>public int displayAll()</li>

</ul>

Displays Name/Address for each table entry. Returns total entry count.

Table will keep a linked list of Nodes. Each entry (from the methods listed above) will be stored in an instance of Node stored in this linked list. The list is maintained in no particular order, but no two Nodes in the list can have the same key field.

Table will also have a (private) field, mark, which is a reference to Node. This field is modified or used by the markToStart, advanceMark, keyAtMark,

and valueAtM ark methods. Together these methods can be used to traverse the list and read the contents of all the entries in the table.

You may add any more methods you need to the Table class but they must be private. The only public methods are those listed above. <em>All </em>instance fields in all classes in your program will be private.

You will notice that this Table class is not specifically an address book but just stores and operates on pairs of strings. You will implement your address book as an instance of Table and will implement the address book operations, listed at the beginning of this page, using public methods of Table.


