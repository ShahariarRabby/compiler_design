<div class="col-md-7 middle-col">
<h1>Compiler Design - Symbol Table</h1>






<p>Symbol table is an important data structure created and maintained by compilers in order to store information about the occurrence of various entities such as variable names, function names, objects, classes, interfaces, etc. Symbol table is used by both the analysis and the synthesis parts of a compiler.</p>
<p>A symbol table may serve the following purposes depending upon the language in hand:</p>
<ul class="list">
<li><p>To store the names of all entities in a structured form at one place.</p></li>
<li><p>To verify if a variable has been declared.</p></li>
<li><p>To implement type checking, by verifying assignments and expressions in the source code are semantically correct.</p></li>
<li><p>To determine the scope of a name (scope resolution).</p></li>
</ul>
<p>A symbol table is simply a table which can be either linear or a hash table</p>






<h2>Implementation</h2>
<p>If a compiler is to handle a small amount of data, then the symbol table can be implemented as an unordered list, which is easy to code, but it is only suitable for small tables only. A symbol table can be implemented in one of the following ways:</p>
<ul class="list">
<li>Linear (sorted or unsorted) list</li>
<li>Binary Search Tree</li>
<li>Hash table</li>
</ul>
<p>Among all, symbol tables are mostly implemented as hash tables, where the source code symbol itself is treated as a key for the hash function and the return value is the information about the symbol.</p>
<h2>Operations</h2>
<p>A symbol table, either linear or hash, should provide the following operations.</p>
<h3>insert()</h3>
<p>This operation is more frequently used by analysis phase, i.e., the first half of the compiler where tokens are identified and names are stored in the table. This operation is used to add information in the symbol table about unique names occurring in the source code. The format or structure in which the names are stored depends upon the compiler in hand.</p>
<p>An attribute for a symbol in the source code is the information associated with that symbol. This information contains the value, state, scope, and type about the symbol. The insert() function takes the symbol and its attributes as arguments and stores the information in the symbol table.</p>




<h3>lookup()</h3>
<p>lookup() operation is used to search a name in the symbol table to determine:</p>
<ul class="list">
<li>if the symbol exists in the table.</li>
<li>if it is declared before it is being used.</li>
<li>if the name is used in the scope.</li>
<li>if the symbol is initialized.</li>
<li>if the symbol declared multiple times.</li>
</ul>
<p>The format of lookup() function varies according to the programming language</p>

<p>This method returns 0 (zero) if the symbol does not exist in the symbol table. If the symbol exists in the symbol table, it returns its attributes stored in the table.</p>




<p>The above program can be represented in a hierarchical structure of symbol tables:</p>
<img src="https://www.tutorialspoint.com/compiler_design/images/symbol_table.jpg" alt="Symbol Table">
<p>The global symbol table contains names for one global variable (int value) and two procedure names, which should be available to all the child nodes shown above. The names mentioned in the pro_one symbol table (and all its child tables) are not available for pro_two symbols and its child tables.</p>
<p>This symbol table data structure hierarchy is stored in the semantic analyzer and whenever a name needs to be searched in a symbol table, it is searched using the following algorithm:</p>
<ul class="list">
<li><p>first a symbol will be searched in the current scope, i.e. current symbol table.</p></li>
<li><p>if a name is found, then search is completed, else it will be searched in the parent symbol table until,</p></li>
<li><p>either the name is found or global symbol table has been searched for the name.</p></li>
</ul>








</div>

## Source: https://www.tutorialspoint.com/compiler_design/compiler_design_symbol_table.htm
