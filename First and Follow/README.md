
<body>
<h2>First and Follow Sets</h2>
<p>When I learn't about first and follow sets at university I found
them difficult to follow, so I have tried to rewrite the rules I was
taught for creating them so that they would be easier to understand. I
hope it helps :)</p>
<p>If you are worried if these rules are actually correct, I have had a
lecturer ask if he can use them in his class so I am assuming they are
correct...</p>
<p> This page was written by <a href="mailto:james@jambe.cjb.net">James Brunskill</a> (<a href="http://www.jambe.co.nz/">www.jambe.co.nz</a>)</p>
<h2>Rules for First Sets</h2>
<p>
</p><ol>
<li> If X is a terminal <strong>then</strong> First(X) is just X!
</li><li> If there is a Production X → ε <strong>then</strong>
add ε
to first(X)
</li><li> If there is a Production X → Y1Y2..Yk<strong>
then</strong> add
first(Y1Y2..Yk) to first(X)
</li><li> First(Y1Y2..Yk) is <strong>either</strong>
<ol>
<li> First(Y1) (if First(Y1) doesn't contain ε)
</li><li><strong>OR</strong>
(if First(Y1) does contain ε) then First (Y1Y2..Yk) is everything in
First(Y1) &lt;except for ε &gt; as well as everything in First(Y2..Yk) </li><li> If First(Y1) First(Y2)..First(Yk) all
contain ε <strong>then</strong>
add ε
to First(Y1Y2..Yk) as well.</li>
</ol>
</li>
</ol>
<p></p>
<p></p><h2>Rules for Follow Sets</h2>
<p>
</p><ol>
<li> First put $ (the end of input marker) in
Follow(S) (S is the start symbol)
</li><li>If there is a production A →
aBb,
(where a can
be a whole string) <strong>then</strong> everything in FIRST(b)
except for ε
is placed in FOLLOW(B).
</li><li>If there is a production A → aB,
<strong>then</strong> everything in FOLLOW(A) is in FOLLOW(B)
</li>
<li>If there is a production A → aBb,
where FIRST(b)
contains ε,
<strong>then</strong> everything in FOLLOW(A) is in FOLLOW(B)</li></ol>
<h2>Here an example for you to follow through.</h2>
<p style="text-align: justify;">The Grammar</p>
<p style="text-align: justify;">E → TE'</p>
<p style="text-align: justify;">E' → +TE'</p>
<p style="text-align: justify;">E' → ε</p>
<p style="text-align: justify;">T → FT'</p>
<p style="text-align: justify;">T' → *FT'</p>
<p style="text-align: justify;">T' → ε</p>
<p style="text-align: justify;">F → (E)</p>
<p style="text-align: justify;">F → id</p>
<p style="text-align: justify;">
<table cellspacing="0" cellpadding="1" border="1">
<tbody><tr>
<td>First Sets</td>
<td>Follow Sets</td></tr>
<tr>
<td valign="top">
<p style="text-align: justify;">We Want to make First sets
so first we list the sets we need</p>
<p style="text-align: justify;">FIRST(E) = {}</p>
<p style="text-align: justify;">FIRST(E') = {}</p>
<p style="text-align: justify;">FIRST(T) = {}</p>
<p style="text-align: justify;">FIRST(T') = {}</p>
<p style="text-align: justify;">FIRST(F) = {}</p>
<p style="text-align: justify;">First We apply rule 2 to T'
→ ε and E' →
ε</p>
<p style="text-align: justify;">FIRST(E) = {}</p>
<p style="text-align: justify;">FIRST(E') = {ε}</p>
<p style="text-align: justify;">FIRST(T) = {}</p>
<p style="text-align: justify;">FIRST(T') = {ε}</p>
<p style="text-align: justify;">FIRST(F) = {}</p>
<p style="text-align: justify;">First We apply rule
3 to T' →
*FT' this rule tells us that we can add everything in First(*FT') into
First(T')</p>
<p style="text-align: justify;">Since First(*) useing rule
1 is * we can add * to First(T')</p>
<p style="text-align: justify;">FIRST(E) = {}</p>
<p style="text-align: justify;">FIRST(E') = {+,ε}</p>
<p style="text-align: justify;">FIRST(T) = {}</p>
<p style="text-align: justify;">FIRST(T') = {*,ε}</p>
<p style="text-align: justify;">FIRST(F) = {}</p>
<p style="text-align: justify;">First We apply rule
3 to T' →
*FT' this rule tells us that we can add everything in First(*FT') into
First(T')</p>
<p style="text-align: justify;">Since First(*) useing rule
1 is * we can add * to First(T')</p>
<p style="text-align: justify;">FIRST(E) = {}</p>
<p style="text-align: justify;">FIRST(E') = {+,ε}</p>
<p style="text-align: justify;">FIRST(T) = {}</p>
<p style="text-align: justify;">FIRST(T') = {*,ε}</p>
<p style="text-align: justify;">FIRST(F) = {}</p>
<p style="text-align: justify;">Two more productions
begin with terminals F →
(E) and F →
id If we apply rule 3 to these we get...</p>
<p style="text-align: justify;">FIRST(E) = {}</p>
<p style="text-align: justify;">FIRST(E') = {+,ε}</p>
<p style="text-align: justify;">FIRST(T) = {}</p>
<p style="text-align: justify;">FIRST(T') = {*,ε}</p>
<p style="text-align: justify;">FIRST(F) = {'(',id}</p>
<p style="text-align: justify;">Next we apply rule 3 to T
→
FT' once again this tells us that we can add First(FT') to First(T)</p>
<p style="text-align: justify;">Since First(F) doesn't
contain ε that
means that First(FT') is just First(F)</p>
<p style="text-align: justify;">FIRST(E) = {}</p>
<p style="text-align: justify;">FIRST(E') = {+,ε}</p>
<p style="text-align: justify;">FIRST(T) = {'(',id}</p>
<p style="text-align: justify;">FIRST(T') = {*,ε}</p>
<p style="text-align: justify;">FIRST(F) = {'(',id}</p>
<p style="text-align: justify;">Lastly we apply rule 3
to E →
TE' once again this tells us that we can add First(TE') to First(E)</p>
<p style="text-align: justify;">Since First(T) doesn't
contain ε that
means that First(TE') is just First(T)</p>
<p style="text-align: justify;">FIRST(E) = {'(',id}</p>
<p style="text-align: justify;">FIRST(E') = {+,ε}</p>
<p style="text-align: justify;">FIRST(T) = {'(',id}</p>
<p style="text-align: justify;">FIRST(T') = {*,ε}</p>
<p style="text-align: justify;">FIRST(F) = {'(',id}</p>
<p style="text-align: justify;">Doing anything else doesn't
change the sets so we are done!</p></td>
<td valign="top">
<p style="text-align: justify;">We want to make Follow sets so first we list the sets we need</p>
<p style="text-align: justify;"> FOLLOW(E) =
{}</p>
<p style="text-align: justify;"> FOLLOW(E') =
{}</p>
<p style="text-align: justify;">FOLLOW(T) ={}</p>
<p style="text-align: justify;"> FOLLOW(T') = {}</p>
<p style="text-align: justify;">FOLLOW(F) = {}</p>
<p style="text-align: justify;">
The
First thing we do is Add $ to the start Symbol 'E'</p>
<p style="text-align: justify;">FOLLOW(E) = {$}</p>
<p style="text-align: justify;">FOLLOW(E') = {}</p>
<p style="text-align: justify;">FOLLOW(T) ={}</p>
<p style="text-align: justify;">FOLLOW(T') = {}</p>
<p style="text-align: justify;">FOLLOW(F) = {}</p>
<p style="text-align: justify;">
Next we
apply rule 2 to E' →+TE' This says that everything in
First(E') except forε should be in
Follow(T)</p>
<p style="text-align: justify;">FOLLOW(E) = {$}</p>
<p style="text-align: justify;">FOLLOW(E') = {}</p>
<p style="text-align: justify;">FOLLOW(T) ={+}</p>
<p style="text-align: justify;">FOLLOW(T') = {}</p>
<p style="text-align: justify;">FOLLOW(F) = {}</p>
<p style="text-align: justify;">
Next we
apply rule 3 to E →TE' This says that we should add
everything in Follow(E) into Follow(E')</p>
<p style="text-align: justify;">FOLLOW(E) = {$}</p>
<p style="text-align: justify;">FOLLOW(E') = {$}</p>
<p style="text-align: justify;">FOLLOW(T) ={+}</p>
<p style="text-align: justify;">FOLLOW(T') = {}</p>
<p style="text-align: justify;">FOLLOW(F) = {}</p>
<p style="text-align: justify;">
Next we
apply rule 3 to T →
FT' This says that we should add everything in Follow(T) into
Follow(T')</p>
<p style="text-align: justify;">FOLLOW(E) = {$}</p>
<p style="text-align: justify;">FOLLOW(E') = {$}</p>
<p style="text-align: justify;">FOLLOW(T) ={+}</p>
<p style="text-align: justify;">FOLLOW(T') = {+}</p>
<p style="text-align: justify;">FOLLOW(F) = {}</p>
<p style="text-align: justify;">
Now we apply rule 2 to T' →*FT' This says that everything in First(T') except for ε should be in Follow(F)</p>
<p style="text-align: justify;">FOLLOW(E) = {$}</p>
<p style="text-align: justify;">FOLLOW(E') = {$}</p>
<p style="text-align: justify;">FOLLOW(T) ={+}</p>
<p style="text-align: justify;">FOLLOW(T') = {+}</p>
<p style="text-align: justify;">FOLLOW(F) = {*}</p>
<p style="text-align: justify;">
Now we apply rule 2 to F → (E) This says that everything in First(')') should be in Follow(E)</p>
<p style="text-align: justify;">FOLLOW(E) = {$,)}</p>
<p style="text-align: justify;">FOLLOW(E') = {$}</p>
<p style="text-align: justify;">FOLLOW(T) ={+}</p>
<p style="text-align: justify;">FOLLOW(T') = {+}</p>
<p style="text-align: justify;">FOLLOW(F) = {*}</p>
<p style="text-align: justify;"> Next we apply rule 3 to E → TE'
This says that we should add everything in Follow(E) into Follow(E')</p>
<p style="text-align: justify;">FOLLOW(E) = {$,)}</p>
<p style="text-align: justify;">FOLLOW(E') = {$,)}</p>
<p style="text-align: justify;">FOLLOW(T) = {+}</p>
<p style="text-align: justify;">FOLLOW(T') = {+}</p>
<p style="text-align: justify;">FOLLOW(F) = {*}</p>
<p style="text-align: justify;">
Next we apply rule 4 to E' → +TE'
This says that we should add everything in Follow(E') into Follow(T) (because First(E') contains ε)
</p>
<p style="text-align: justify;">FOLLOW(E) = {$,)}</p>
<p style="text-align: justify;">FOLLOW(E') = {$,)}</p>
<p style="text-align: justify;">FOLLOW(T) = {+,$,)}</p>
<p style="text-align: justify;">FOLLOW(T') = {+}</p>
<p style="text-align: justify;">FOLLOW(F) = {*}</p>
<p style="text-align: justify;">
Next we apply rule 3 to T → FT' This says that we should add everything in Follow(T) into Follow(T')</p>
<p style="text-align: justify;">FOLLOW(E) = {$,)}</p>
<p style="text-align: justify;">FOLLOW(E') = {$,)}</p>
<p style="text-align: justify;">FOLLOW(T) = {+,$,)}</p>
<p style="text-align: justify;">FOLLOW(T') = {+,$,)}</p>
<p style="text-align: justify;">FOLLOW(F) = {*}</p>
<p style="text-align: justify;">
Finaly we apply rule 4 to T' → *FT' This says that we should add everything in Follow(T') into Follow(F)</p>
<p style="text-align: justify;">FOLLOW(E) = {$,)}</p>
<p style="text-align: justify;">FOLLOW(E') = {$,)}</p>
<p style="text-align: justify;">FOLLOW(T) = {+,$,)}</p>
<p style="text-align: justify;">FOLLOW(T') = {+,$,)}</p>
<p style="text-align: justify;">FOLLOW(F) = {*,+,$,)}</p></td></tr></tbody></table></p>
<p> This page was written by <a href="mailto:james@jambe.cjb.net">James Brunskill</a> (<a href="http://www.jambe.co.nz/">www.jambe.co.nz</a>)</p>

</body>