<h1>JavaScript Regular Expressions (Regex)</h1>

<p>Regular expressions (regex) are patterns used to match character combinations in strings. They are a powerful tool for searching, replacing, and validating string data.</p>

<h2>Basics</h2>
<p>Regular expressions consist of literals and metacharacters. Here are some basic components:</p>
<ul>
  <li><strong>Literals</strong>: Match the exact characters.</li>
  <li><strong>Metacharacters</strong>: Special characters with specific meanings (e.g., <code>.</code>, <code>^</code>, <code>$</code>, <code>\d</code>, <code>\w</code>, <code>\s</code>).</li>
</ul>

<h2>Quantifiers</h2>
<p>Quantifiers specify the number of occurrences to match:</p>
<ul>
  <li><code>*</code>: Matches 0 or more times.</li>
  <li><code>+</code>: Matches 1 or more times.</li>
  <li><code>?</code>: Matches 0 or 1 time.</li>
  <li><code>{n}</code>: Matches exactly <code>n</code> times.</li>
  <li><code>{n,}</code>: Matches at least <code>n</code> times.</li>
  <li><code>{n,m}</code>: Matches between <code>n</code> and <code>m</code> times.</li>
</ul>

<h2>Character Classes</h2>
<p>Character classes define a set of characters:</p>
<ul>
  <li><code>[abc]</code>: Matches any of <code>a</code>, <code>b</code>, or <code>c</code>.</li>
  <li><code>[a-z]</code>: Matches any lowercase letter.</li>
  <li><code>[^abc]</code>: Matches any character except <code>a</code>, <code>b</code>, or <code>c</code>.</li>
</ul>

<h2>Groups and Alternation</h2>
<p>Grouping and alternation allow for more complex patterns:</p>
<ul>
  <li><code>(abc)</code>: Groups characters as a single unit.</li>
  <li><code>a|b</code>: Matches either <code>a</code> or <code>b</code>.</li>
</ul>

<h2>Escape Sequences</h2>
<p>Escape sequences are used to match special characters:</p>
<ul>
  <li><code>\\</code>: Matches a backslash <code>\</code>.</li>
  <li><code>\.</code>: Matches a period <code>.</code>.</li>
  <li><code>\^</code>: Matches a caret <code>^</code>.</li>
  <li><code>\$</code>: Matches a dollar sign <code>$</code>.</li>
  <li><code>\*</code>: Matches an asterisk <code>*</code>.</li>
  <li><code>\+</code>: Matches a plus sign <code>+</code>.</li>
  <li><code>\?</code>: Matches a question mark <code>?</code>.</li>
  <li><code>\(</code>: Matches an opening parenthesis <code>(</code>.</li>
  <li><code>\)</code>: Matches a closing parenthesis <code>)</code>.</li>
  <li><code>\{</code>: Matches an opening curly brace <code>{</code>.</li>
  <li><code>\}</code>: Matches a closing curly brace <code>}</code>.</li>
  <li><code>\[</code>: Matches an opening square bracket <code>[</code>.</li>
  <li><code>\]</code>: Matches a closing square bracket <code>]</code>.</li>
  <li><code>\|</code>: Matches a vertical bar <code>|</code>.</li>
</ul>

<h2>Matching the Start and End of a String</h2>
<p>Regex patterns to match the start and end of a string:</p>
<ul>
  <li><strong>Start of a String (<code>^</code>)</strong>:
    <pre><code>
const regex = /^Hello/;
console.log(regex.test("Hello, world!")); // true
console.log(regex.test("Say Hello!")); // false
    </code></pre>
    <p>This regex matches strings that start with "Hello".</p>
  </li>
  <li><strong>End of a String (<code>$</code>)</strong>:
    <pre><code>
const regex = /world!$/;
console.log(regex.test("Hello, world!")); // true
console.log(regex.test("Hello, world")); // false
    </code></pre>
    <p>This regex matches strings that end with "world!".</p>
  </li>
</ul>

<h2>Matching Spaces</h2>
<p>Regex patterns to match spaces and whitespace characters:</p>
<ul>
  <li><strong>Whitespace Characters (<code>\s</code>)</strong>:
    <pre><code>
const regex = /\s/;
console.log(regex.test("Hello world")); // true
console.log(regex.test("Helloworld")); // false
    </code></pre>
    <p>This regex matches any string that contains at least one whitespace character.</p>
  </li>
  <li><strong>Specific Spaces</strong>:
    <pre><code>
const regex = / +/; // Matches one or more spaces
console.log("Hello   world".match(regex)); // ["   "]
    
const regex2 = /\s{2}/; // Matches exactly two spaces
console.log(regex2.test("Hello  world")); // true
console.log(regex2.test("Hello world")); // false
    </code></pre>
    <p>The first regex matches one or more spaces, while the second regex matches exactly two spaces.</p>
  </li>
</ul>

<h2>Examples</h2>
<ol>
  <li><strong>Simple Match</strong>:
    <pre><code>
const regex = /abc/;
console.log(regex.test("abcdef")); // true
    </code></pre>
  </li>
  <li><strong>Using Metacharacters</strong>:
    <pre><code>
const regex = /\d{3}-\d{2}-\d{4}/;
console.log(regex.test("123-45-6789")); // true
    </code></pre>
  </li>
  <li><strong>Matching Email Addresses</strong>:
    <pre><code>
const emailRegex = /^[\w.-]+@[a-zA-Z\d.-]+\.[a-zA-Z]{2,}$/;
console.log(emailRegex.test("example@example.com")); // true
    </code></pre>
  </li>
  <li><strong>Extracting Parts of a String</strong>:
    <pre><code>
const regex = /(\d{3})-(\d{2})-(\d{4})/;
const match = "123-45-6789".match(regex);
console.log(match); // ["123-45-6789", "123", "45", "6789"]
    </code></pre>
  </li>
  <li><strong>Replacing Parts of a String</strong>:
    <pre><code>
const regex = /apples/gi;
const str = "Apples are good. I like apples.";
const newStr = str.replace(regex, "oranges");
console.log(newStr); // "oranges are good. I like oranges."
    </code></pre>
  </li>
</ol>
