<h1>useEffect in React</h1>

<p><code>useEffect</code> is a React hook that allows you to perform side effects in your components, such as fetching data, updating the DOM, or subscribing to events. It runs after the component has been rendered to the screen, ensuring side effects don’t block the UI rendering.</p>

<h2>Basic Syntax</h2>
<pre><code>useEffect(() => {
  // Side effect code here
}, [dependencies]);  // Optional: array of dependencies</code></pre>

<p>The <strong>dependencies array</strong> determines when the effect should run. Depending on how it is used, the effect can run differently.</p>

<h2>How useEffect Works</h2>

<h3>1. No Dependency Passed</h3>
<p>If no dependency array is passed, <code>useEffect</code> will run on every render.</p>
<pre><code>useEffect(() => {
  console.log('Runs on every render');
});</code></pre>

<h3>2. Empty Dependency Array</h3>
<p>If an empty array is passed, <code>useEffect</code> will run only once when the component first mounts.</p>
<pre><code>useEffect(() => {
  console.log('Runs only on the first render');
}, []);</code></pre>

<h3>3. Props or State Values in the Dependency Array</h3>
<p>If specific props or state variables are included in the dependency array, <code>useEffect</code> will run on the initial render and whenever any of the specified dependencies change.</p>
<pre><code>useEffect(() => {
  console.log('Runs on first render and when prop or state changes');
}, [prop, state]);</code></pre>

<h2>The Component Render Cycle in React</h2>
<p>The component render cycle describes how React updates components and the DOM.</p>

<h3>1. Initial Render</h3>
<ul>
  <li>The component is rendered for the first time.</li>
  <li>React calls the component function, runs hooks like <code>useState</code> and <code>useEffect</code>, and updates the DOM based on the returned JSX.</li>
</ul>

<h3>2. Subsequent Renders</h3>
<ul>
  <li>When state or props change, React re-renders the component.</li>
  <li>The component function runs again, and the updated JSX is returned.</li>
</ul>

<h3>3. useEffect Execution</h3>
<ul>
  <li>After each render (including the initial render), <code>useEffect</code> is called.</li>
  <li>By default, it runs after the render to avoid blocking the rendering process.</li>
  <li>You can control when <code>useEffect</code> runs by passing a dependency array (e.g., <code>[]</code> for once, or specific variables to track their changes).</li>
</ul>

<h2>Key Concepts</h2>
<ol>
  <li><strong>Side Effects</strong>: Operations that interact with external systems like fetching data, manipulating the DOM, or subscribing to events.</li>
  <li><strong>Dependencies</strong>: The array of values that determines when <code>useEffect</code> runs.</li>
  <li><strong>Render Cycle</strong>: The phases during which React renders and updates the component.</li>
  <li><strong>Performance</strong>: Running side effects after the render prevents blocking the initial UI load.</li>
</ol>
