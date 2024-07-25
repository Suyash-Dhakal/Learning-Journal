<h1>Learning Journal</h1>

<p>Welcome to my Learning Journal! Here, I will be documenting all my learnings across various domains in this repository.</p>

<h2>JavaScript Regular Expressions (Regex)</h2>

<p>Regular expressions (regex) are patterns used to match character combinations in strings. They are powerful tools for searching, validating, and manipulating text.</p>

<h3>Basics of Regex</h3>

<ul>
  <li><strong>Literals:</strong> Match exact characters. Example: <code>/abc/</code> matches "abc".</li>
  <li><strong>Metacharacters:</strong> Special characters with specific meanings:
    <ul>
      <li><code>.</code> matches any character except newline.</li>
      <li><code>^</code> matches the start of a string.</li>
      <li><code>$</code> matches the end of a string.</li>
      <li><code>\d</code> matches any digit.</li>
      <li><code>\w</code> matches any word character (alphanumeric plus underscore).</li>
      <li><code>\s</code> matches any whitespace character.</li>
    </ul>
  </li>
  <li><strong>Quantifiers:</strong> Specify the number of occurrences:
    <ul>
      <li><code>*</code> matches 0 or more times.</li>
      <li><code>+</code> matches 1 or more times.</li>
      <li><code>?</code> matches 0 or 1 time.</li>
      <li><code>{n}</code> matches exactly n times.</li>
      <li><code>{n,}</code> matches at least n times.</li>
      <li><code>{n,m}</code> matches between n and m times.</li>
    </ul>
  </li>
  <li><strong>Character Classes:</strong> Define a set of characters:
    <ul>
      <li><code>[abc]</code> matches any of a, b, or c.</li>
      <li><code>[a-z]</code> matches any lowercase letter.</li>
      <li><code>[^abc]</code> matches any character except a, b, or c.</li>
    </ul>
  </li>
  <li><strong>Groups and Alternation:</strong>
    <ul>
      <li><code>(abc)</code> groups characters as a single unit.</li>
      <li><code>a|b</code> matches either a or b.</li>
    </ul>
  </li>
</ul>

<h3>Escape Sequences in Regex</h3>

<p>Escape sequences allow you to use special characters in your regex patterns. Here are some common escape sequences:</p>

<ul>
  <li><code>\.</code> matches a literal dot.</li>
  <li><code>\*</code> matches a literal asterisk.</li>
  <li><code>\+</code> matches a literal plus sign.</li>
  <li><code>\?</code> matches a literal question mark.</li>
  <li><code>\d</code> matches any digit (0-9).</li>
  <li><code>\w</code> matches any word character (alphanumeric plus underscore).</li>
  <li><code>\s</code> matches any whitespace character.</li>
  <li><code>\\</code> matches a literal backslash.</li>
</ul>

<h3>Examples</h3>

<ol>
  <li><strong>Simple Match:</strong>
    <pre><code>const regex = /abc/;
console.log(regex.test("abcdef")); // true
    </code></pre>
  </li>
  <li><strong>Using Metacharacters:</strong>
    <pre><code>const regex = /\d{3}-\d{2}-\d{4}/;
console.log(regex.test("123-45-6789")); // true
    </code></pre>
  </li>
  <li><strong>Matching Email Addresses:</strong>
    <pre><code>const emailRegex = /^[\w.-]+@[a-zA-Z\d.-]+\.[a-zA-Z]{2,}$/;
console.log(emailRegex.test("example@example.com")); // true
    </code></pre>
  </li>
  <li><strong>Extracting Parts of a String:</strong>
    <pre><code>const regex = /(\d{3})-(\d{2})-(\d{4})/;
const match = "123-45-6789".match(regex);
console.log(match); // ["123-45-6789", "123", "45", "6789"]
    </code></pre>
  </li>
  <li><strong>Replacing Parts of a String:</strong>
    <pre><code>const regex = /apples/gi;
const str = "Apples are good. I like apples.";
const newStr = str.replace(regex, "oranges");
console.log(newStr); // "oranges are good. I like oranges."
    </code></pre>
  </li>
</ol>

<h3>Common Use Cases</h3>

<ul>
  <li><strong>Validation:</strong> Checking if a string follows a specific format (e.g., email, phone number).</li>
  <li><strong>Searching:</strong> Finding substrings within a string.</li>
  <li><strong>Replacing:</strong> Modifying parts of a string.</li>
  <li><strong>Extracting:</strong> Pulling out specific parts of a string.</li>
</ul>
