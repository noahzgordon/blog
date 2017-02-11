<h1 id="learning-haskell...-with-elm">Learning Haskell… With Elm!</h1>
<p>Haskell has an intense learning curve. Anyone who’s gotten started with it knows this well. The shangri-la of pure, functional programming languages has garnered a nasty reputation for inaccessibility.</p>
<p>But Haskell is also an incredibly interesting and, believe it or not, useful language for building fast, reliable applications. Learning it will both add a new tool to your belt and change the way you program in more familiar languages.</p>
<p>Haskelll was the third programming language I began learning; that was several years ago, and I still consider myself an amateur. It’s tough stuff. After learning the basics I hit a roadblock. And then I found Elm.</p>
<p>Elm, in contrast to Haskell, has generated a lot of positive press around not only its reliability, but also its approachability. It’s a language built with the programmer’s experience as a top priority. After familiarizing myself with Elm in a relatively short amount of time, I felt empowered to dust off the ol’ Haskell tomes and get back to it.</p>
<p>And guess what? It was a lot easier!</p>
<p>Elm borrows a lot of ideas from Haskell; the similarities are abundant. By focusing on usability, Elm familiarizes you with FP concepts that are traditionally hard to learn or teach. If you learn best by doing, Elm is the ramp you need to ease into Haskell’s learning cliff.</p>
<p>Let’s start with some basics.</p>
<p><a href="https://guide.elm-lang.org/install.html">Elm Installation</a><br>
<a href="https://www.haskell.org/platform/">Haskell Installation</a></p>
<h2 id="the-similarities">The Similarities</h2>
<h3 id="comments">Comments</h3>
<p>Every programming language needs comments, right? Good news: comments in Haskell and Elm look exactly the same.</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- They both look like this :D</span>
<span class="token comment" spellcheck="true">{- Or they can extend to
   multiple lines!
-}</span>
</code></pre>
<p>Fair enough. What else is the same?</p>
<h3 id="functions">Functions</h3>
<p>Haskell and Elm both draw most of their syntax and many of their core concepts from a common ancestor called <a href="https://en.wikipedia.org/wiki/ML_(programming_language)">ML</a>. This means that function definitions and type declarations look remarkably similar in the two languages.</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- elm</span>
<span class="token hvariable">stringThings</span> <span class="token operator">:</span> <span class="token constant">String</span> <span class="token operator">-&gt;</span> <span class="token constant">String</span> <span class="token operator">-&gt;</span> <span class="token constant">String</span>
<span class="token hvariable">stringThings</span> <span class="token hvariable">stringA</span> <span class="token hvariable">stringB</span> <span class="token operator">=</span> <span class="token operator">~~</span><span class="token hvariable">some</span> <span class="token hvariable">definition</span><span class="token operator">~~</span>

<span class="token comment" spellcheck="true">-- haskell</span>
<span class="token hvariable">stringThings</span> <span class="token operator">::</span> <span class="token constant">String</span> <span class="token operator">-&gt;</span> <span class="token constant">String</span> <span class="token operator">-&gt;</span> <span class="token constant">String</span>
<span class="token hvariable">stringThings</span> <span class="token hvariable">stringA</span> <span class="token hvariable">stringB</span> <span class="token operator">=</span> <span class="token operator">~~</span><span class="token hvariable">some</span> <span class="token hvariable">definition</span><span class="token operator">~~</span>
</code></pre>
<p>Functions in both languages are declared in the same way and automatically curried, meaning that you can apply arguments to them one at a time rather than all at once. They can also be applied and composed in much of the same way (but more on that later).</p>
<p>You’ll notice one difference in the above example: Elm type signatures are denoted with a single <code>:</code>, while Haskell opts for the double <code>::</code>. It’ll take a bit of getting used to. In Haskell and Elm, type declaration and array concatenation are swapped.</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- elm</span>
<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">2</span><span class="token punctuation">,</span><span class="token number">3</span><span class="token punctuation">,</span><span class="token number">4</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token number">1</span> <span class="token operator">::</span> <span class="token number">2</span> <span class="token operator">::</span> <span class="token number">3</span> <span class="token operator">::</span> <span class="token number">4</span> <span class="token operator">::</span> <span class="token punctuation">[</span><span class="token punctuation">]</span>

<span class="token comment" spellcheck="true">-- haskell</span>
<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">2</span><span class="token punctuation">,</span><span class="token number">3</span><span class="token punctuation">,</span><span class="token number">4</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token number">1</span> <span class="token operator">:</span> <span class="token number">2</span> <span class="token operator">:</span> <span class="token number">3</span> <span class="token operator">:</span> <span class="token number">4</span> <span class="token operator">:</span> <span class="token punctuation">[</span><span class="token punctuation">]</span>
</code></pre>
<p>Yes, it’s annoying, but stick with me!</p>
<h3 id="lambdas-types-and-records">Lambdas, Types and Records</h3>
<p>You can declare anonymous functions in Haskell and Elm in the same way.</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- this is valid in both languages!</span>
<span class="token punctuation">(</span><span class="token operator">\</span><span class="token hvariable">a</span> <span class="token hvariable">b</span> <span class="token operator">-&gt;</span> <span class="token hvariable">a</span> <span class="token operator">+</span> <span class="token hvariable">b</span><span class="token punctuation">)</span> <span class="token number">2</span> <span class="token number">4</span>
</code></pre>
<p>The way you declare new types in Haskell is also very similar to Elm.</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- elm</span>
<span class="token keyword">type</span> <span class="token hvariable">alias</span> <span class="token constant">Name</span> <span class="token operator">=</span> <span class="token constant">String</span>
<span class="token keyword">type</span> <span class="token constant">ForceUser</span> <span class="token operator">=</span> <span class="token constant">Jedi</span> <span class="token constant">Name</span> <span class="token operator">|</span> <span class="token constant">Sith</span> <span class="token constant">Name</span>

<span class="token comment" spellcheck="true">-- haskell</span>
<span class="token keyword">type</span> <span class="token constant">Name</span> <span class="token operator">=</span> <span class="token constant">String</span>
<span class="token keyword">data</span> <span class="token constant">ForceUser</span> <span class="token operator">=</span> <span class="token constant">Jedi</span> <span class="token constant">Name</span> <span class="token operator">|</span> <span class="token constant">Sith</span> <span class="token constant">Name</span>
</code></pre>
<p>Again, the name swapping is sort of confusing, but you can see support for type aliases (<code>type</code>), and union/sum types (<code>data</code>) in Haskell.</p>
<p>You can also use record syntax when declaring types in Haskell; although, unlike in Elm, Haskell records are not first-class citizens and can be thought of as syntactic sugar on top of a union type.</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- haskell</span>
<span class="token keyword">data</span> <span class="token constant">Wookie</span> <span class="token operator">=</span> <span class="token constant">Wookie</span> <span class="token punctuation">{</span> <span class="token hvariable">name</span> <span class="token operator">::</span> <span class="token constant">String</span>
                     <span class="token punctuation">,</span> <span class="token hvariable">weapon</span> <span class="token operator">::</span> <span class="token constant">Weapon</span>
                     <span class="token punctuation">,</span> <span class="token hvariable">fuzzy</span> <span class="token operator">::</span> <span class="token constant">Bool</span>
                     <span class="token punctuation">}</span>

<span class="token hvariable">chewie</span> <span class="token operator">::</span> <span class="token constant">Wookie</span>
<span class="token hvariable">chewie</span> <span class="token operator">=</span> <span class="token constant">Wookie</span> <span class="token punctuation">{</span> <span class="token hvariable">name</span> <span class="token operator">=</span> <span class="token string">"Chewbacca"</span>
                <span class="token punctuation">,</span> <span class="token hvariable">weapon</span> <span class="token operator">=</span> <span class="token constant">Bowcaster</span>
                <span class="token punctuation">,</span> <span class="token hvariable">fuzzy</span> <span class="token operator">=</span> <span class="token constant">True</span>
                <span class="token punctuation">}</span>
</code></pre>
<h2 id="the-differences">The Differences</h2>
<h3 id="cases-vs.-pattern-matching-and--guards">Cases vs. Pattern Matching and  Guards</h3>
<p>In Elm, your primary tool for matching on sum types and destructuring arguments is the <code>case</code> statement.</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- elm</span>
<span class="token hvariable">greet</span> <span class="token operator">:</span> <span class="token constant">ForceUser</span> <span class="token operator">-&gt;</span> <span class="token constant">String</span>
<span class="token hvariable">greet</span> <span class="token hvariable">user</span> <span class="token operator">=</span>
  <span class="token keyword">case</span> <span class="token hvariable">user</span> <span class="token keyword">of</span>
    <span class="token punctuation">(</span><span class="token constant">Jedi</span> <span class="token hvariable">name</span><span class="token punctuation">)</span> <span class="token operator">-&gt;</span>
      <span class="token string">"Greetings, Master "</span> <span class="token operator">++</span> <span class="token hvariable">name</span>
    <span class="token punctuation">(</span><span class="token constant">Sith</span> <span class="token hvariable">name</span><span class="token punctuation">)</span> <span class="token operator">-&gt;</span>
      <span class="token string">"I feel the dark side in you, "</span> <span class="token operator">++</span> <span class="token hvariable">name</span>
</code></pre>
<p>Haskell has a number of constructs you can use to achieve the same end. Case statements are supported using exactly the same syntax, though you may also want to consider <a href="https://en.wikibooks.org/wiki/Haskell/Pattern_matching">pattern matching.</a> Pattern matching is a concise, powerful Haskell feature that isn’t supported by Elm. Like Elm’s cases, it also enables argument destructuring.</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- haskell</span>
<span class="token hvariable">greet</span> <span class="token operator">::</span> <span class="token constant">ForceUser</span> <span class="token operator">-&gt;</span> <span class="token constant">String</span>
<span class="token hvariable">greet</span> <span class="token punctuation">(</span><span class="token constant">Jedi</span> <span class="token hvariable">name</span><span class="token punctuation">)</span> <span class="token operator">=</span> <span class="token string">"Greetings, Master "</span> <span class="token operator">++</span> <span class="token hvariable">name</span>
<span class="token hvariable">greet</span> <span class="token punctuation">(</span><span class="token constant">Sith</span> <span class="token hvariable">name</span><span class="token punctuation">)</span> <span class="token operator">=</span> <span class="token string">"I feel the dark side in you, "</span> <span class="token operator">++</span> <span class="token hvariable">name</span>
</code></pre>
<p>There is also an alternative syntax for conditional logic in Haskell called <a href="https://en.wikibooks.org/wiki/Haskell/Control_structures#if_and_guards_revisited">guards</a>. They’re useful as an alternative to <code>if/else</code> when comparing values rather than matching sum types. They look like this:</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- haskell</span>
<span class="token hvariable">betweenTwoAndSix</span> <span class="token operator">::</span> <span class="token constant">Int</span> <span class="token operator">-&gt;</span> <span class="token constant">Bool</span>
<span class="token hvariable">betweenTwoAndSix</span> <span class="token hvariable">num</span>
  <span class="token operator">|</span> <span class="token hvariable">num</span> <span class="token operator">&lt;</span> <span class="token number">2</span>   <span class="token operator">=</span> <span class="token constant">False</span>
  <span class="token operator">|</span> <span class="token hvariable">num</span> <span class="token operator">&gt;</span> <span class="token number">6</span>   <span class="token operator">=</span> <span class="token constant">False</span>
  <span class="token operator">|</span> <span class="token builtin">otherwise</span> <span class="token operator">=</span> <span class="token constant">True</span>
</code></pre>
<h3 id="letin-vs.-where">Let/In vs. Where</h3>
<p>In Elm, you can declare scoped values local to your function using <code>let/in</code> syntax.</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- elm</span>
<span class="token hvariable">addTwo</span> <span class="token operator">:</span> <span class="token constant">Int</span> <span class="token operator">-&gt;</span> <span class="token constant">Int</span>
<span class="token hvariable">addTwo</span> <span class="token hvariable">num</span> <span class="token operator">=</span>
  <span class="token keyword">let</span>
    <span class="token hvariable">numToAdd</span> <span class="token operator">=</span> <span class="token number">2</span>
  
  <span class="token keyword">in</span>
    <span class="token hvariable">num</span> <span class="token operator">+</span> <span class="token hvariable">numToAdd</span>
</code></pre>
<p>Haskell supports the same syntactic construct and adds another called <code>where</code>. The following two function definitions are equivalent:</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- haskell</span>
<span class="token hvariable">addTwo</span> <span class="token operator">::</span> <span class="token constant">Int</span> <span class="token operator">-&gt;</span> <span class="token constant">Int</span>
<span class="token hvariable">addTwo</span> <span class="token hvariable">num</span> <span class="token operator">=</span>
  <span class="token keyword">let</span> <span class="token hvariable">numToAdd</span> <span class="token operator">=</span> <span class="token number">2</span>
  <span class="token keyword">in</span> <span class="token hvariable">num</span> <span class="token operator">+</span> <span class="token hvariable">numToAdd</span>

<span class="token hvariable">addTwoWhere</span> <span class="token operator">::</span> <span class="token constant">Int</span> <span class="token operator">-&gt;</span> <span class="token constant">Int</span>
<span class="token hvariable">addTwoWhere</span> <span class="token hvariable">num</span> <span class="token operator">=</span> <span class="token hvariable">numToAdd</span> <span class="token operator">+</span> <span class="token hvariable">num</span>
  <span class="token keyword">where</span> <span class="token hvariable">numToAdd</span> <span class="token operator">=</span> <span class="token number">2</span>
</code></pre>
<p>In Haskell, as in Elm, white space matters when using these constructs!</p>
<h3 id="application-and-composition">Application and Composition</h3>
<p>Finally, let’s talk about operators. In Elm, you may be familiar with <code>&lt;|</code> and <code>|&gt;</code> as directional function application operators (do everything on this side first). Basic Haskell (as defined by GHCI’s <code>Prelude</code>) only supports right-associative function application with <code>$</code>. In order words, Elm’s <code>&lt;|</code> == Haskell’s <code>$</code>.</p>
<p>In Elm we also have <code>&lt;&lt;</code> and <code>&gt;&gt;</code>, which we use to compose functions. Haskell’s equivalent is called the “dot operator” and defines right-associative composition. Elm’s <code>&lt;&lt;</code> == Haskell’s <code>.</code>.</p>
<pre class=" language-haskell"><code class="prism  language-haskell"><span class="token comment" spellcheck="true">-- elm</span>
<span class="token hvariable">addTwo</span> <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token operator">+</span><span class="token punctuation">)</span> <span class="token number">2</span>
<span class="token hvariable">addThree</span> <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token operator">+</span><span class="token punctuation">)</span> <span class="token number">3</span>
<span class="token hvariable">addFive</span> <span class="token operator">=</span> <span class="token hvariable">addTwo</span> <span class="token operator">&lt;&lt;</span> <span class="token hvariable">addThree</span>
<span class="token hvariable">addTenThenAddFiv</span> <span class="token hvariable">num</span> <span class="token operator">=</span> <span class="token hvariable">addFive</span> <span class="token operator">&lt;|</span> <span class="token hvariable">num</span> <span class="token operator">+</span> <span class="token number">10</span>

<span class="token comment" spellcheck="true">-- haskell</span>
<span class="token hvariable">addTwo</span> <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token operator">+</span><span class="token punctuation">)</span> <span class="token number">2</span>
<span class="token hvariable">addThree</span> <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token operator">+</span><span class="token punctuation">)</span> <span class="token number">3</span>
<span class="token hvariable">addFive</span> <span class="token operator">=</span> <span class="token hvariable">addTwo</span><span class="token operator"> . </span><span class="token hvariable">addThree</span>
<span class="token hvariable">addTenThenAddFiv</span> <span class="token hvariable">num</span> <span class="token operator">=</span> <span class="token hvariable">addFive</span> <span class="token operator">$</span> <span class="token hvariable">num</span> <span class="token operator">+</span> <span class="token number">10</span>
</code></pre>
<p>Note: There are other Haskell libraries that add left-associative appication and composition, but we’re going to stick to the <code>Prelude</code> for now.</p>
<h2 id="review">Review</h2>
<p>Here’s a handy table comparing different syntaxes and features in Haskell and Elm:</p>
<table>
<thead>
<tr>
<th>elm</th>
<th>haskell</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>-- one-line comment</code></td>
<td><code>--one-line comment</code></td>
</tr>
<tr>
<td><code>{- multi-line comment -}</code></td>
<td><code>{- multi-line comment -}</code></td>
</tr>
<tr>
<td><code>func : String -&gt; String</code></td>
<td><code>func :: String -&gt; String</code></td>
</tr>
<tr>
<td><code>1 :: 2 :: 3 :: []</code></td>
<td><code>1 : 2 : 3 : []</code></td>
</tr>
<tr>
<td><code>(\a b -&gt; a + b) 2 4</code></td>
<td><code>(\a b -&gt; a + b) 2 4</code></td>
</tr>
<tr>
<td><code>type alias Name = String</code></td>
<td><code>type Name = String</code></td>
</tr>
<tr>
<td><code>type ForceUser = Jedi | Sith</code></td>
<td><code>data ForceUser = Jedi | Sith</code></td>
</tr>
<tr>
<td><code>addFive &lt;| num + 10</code></td>
<td>}<code>addFive $ num + 10</code></td>
</tr>
<tr>
<td><code>addTwo &lt;&lt; addThree</code></td>
<td><code>addTwo . addThree</code></td>
</tr>
</tbody>
</table>
<h2 id="what-else">What Else?</h2>
<p>Of course, because Haskell has been in development about 20 years longer than Elm has, it has a great berth of features that aren’t a part of Elm. The purpose of this post is to get you familiarized with the basics and show that if you know Elm, you’re already a good chunk of the way there.</p>
<p>Haskell’s “Type Classes” define constraints around groups of types and are a big part of what makes the language so powerful. If you’ve seen the <code>comparable</code> keyword in Elm, you already have an idea of what a Type Class is: it groups all of the types that can be compared (<code>String</code>, <code>Int</code>, <code>Float</code>, <code>Tuple</code>, etc) and allows type signatures to leverage that grouping. In Haskell, you can define these groupings yourself or add your own types to them. In addition, each Type Class comes with free utility functions!</p>
<p>If you’ve been using Elm for a while, you might have noticed that a number of the core libraries’ modules have a <code>map</code> function with a similar type signature. How this function relates to Haskell’s type classes will be the subject of the next blog post!</p>
