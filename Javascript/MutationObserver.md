<h1>JavaScript MutationObserver</h1>

<p>The <code>MutationObserver</code> is a built-in JavaScript object that provides a way to watch for changes to the DOM tree. It is used to react to changes in a more efficient and performant manner than traditional methods like <code>setInterval</code> or <code>DOMNodeInserted</code>.</p>

<h2>Basic Usage of MutationObserver</h2>

<p>Here's how to use <code>MutationObserver</code>:</p>

<ol>
  <li><strong>Creating a MutationObserver</strong>
    <pre><code>
const observer = new MutationObserver((mutationsList, observer) => {
    for (const mutation of mutationsList) {
        console.log(mutation);
    }
});
    </code></pre>
  </li>
  <li><strong>Configuring the Observer</strong>
    <pre><code>
const config = {
    childList: true, // Observe changes to the children of the target
    attributes: true, // Observe changes to attributes of the target
    subtree: true, // Observe changes to all descendants of the target
    characterData: true // Observe changes to the text content of the target
};
    </code></pre>
  </li>
  <li><strong>Starting Observation</strong>
    <pre><code>
const targetNode = document.getElementById('someElement');
observer.observe(targetNode, config);
    </code></pre>
  </li>
  <li><strong>Stopping Observation</strong>
    <pre><code>
observer.disconnect();
    </code></pre>
  </li>
</ol>

<h2>Example: Observing Changes to a DOM Element</h2>

<p>Here’s a complete example of using <code>MutationObserver</code> to observe changes to a specific DOM element:</p>

<pre><code>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MutationObserver Example</title>
</head>
<body>
    <div id="observedElement">
        <p>Initial content</p>
    </div>
    <button id="changeButton">Change Content</button>
    <script>
        // Callback function to execute when mutations are observed
        const callback = (mutationsList, observer) => {
            for (const mutation of mutationsList) {
                console.log(mutation);
                if (mutation.type === 'childList') {
                    console.log('A child node has been added or removed.');
                } else if (mutation.type === 'attributes') {
                    console.log(`The ${mutation.attributeName} attribute was modified.`);
                }
            }
        };

        // Create a new MutationObserver instance with the callback
        const observer = new MutationObserver(callback);

        // Specify what to observe
        const config = { attributes: true, childList: true, subtree: true };

        // Target node to observe
        const targetNode = document.getElementById('observedElement');

        // Start observing the target node
        observer.observe(targetNode, config);

        // Example of modifying the DOM
        document.getElementById('changeButton').addEventListener('click', () => {
            const newElement = document.createElement('p');
            newElement.textContent = 'New content';
            targetNode.appendChild(newElement);
            targetNode.setAttribute('data-new-attribute', 'newValue');
        });

        // To stop observing, you can use:
        // observer.disconnect();
    </script>
</body>
</html>
</code></pre>

<h2>Explanation</h2>

<p>1. <strong>Define the Callback Function</strong>: The <code>callback</code> function is where you handle the observed mutations. It logs each mutation and prints specific messages based on the type of mutation.</p>
<pre><code>
const callback = (mutationsList, observer) => {
    for (const mutation of mutationsList) {
        console.log(mutation);
        if (mutation.type === 'childList') {
            console.log('A child node has been added or removed.');
        } else if (mutation.type === 'attributes') {
            console.log(`The ${mutation.attributeName} attribute was modified.`);
        }
    }
};
</code></pre>

<p>2. <strong>Create the MutationObserver Instance</strong>: You create the <code>MutationObserver</code> instance by passing the callback function to its constructor.</p>
<pre><code>
const observer = new MutationObserver(callback);
</code></pre>

<p>3. <strong>Specify the Configuration</strong>: The <code>config</code> object specifies what types of mutations you want to observe. In this case, we are observing changes to attributes, child nodes, and all descendants (<code>subtree</code>).</p>
<pre><code>
const config = { attributes: true, childList: true, subtree: true };
</code></pre>

<p>4. <strong>Start Observing</strong>: Use the <code>observe</code> method to start observing the target node (<code>#observedElement</code>) with the specified configuration.</p>
<pre><code>
const targetNode = document.getElementById('observedElement');
observer.observe(targetNode, config);
</code></pre>

<p>5. <strong>Modify the DOM</strong>: The button click event adds a new <code>&lt;p&gt;</code> element and sets a new attribute on the target node. These changes will trigger the observer's callback.</p>
<pre><code>
document.getElementById('changeButton').addEventListener('click', () => {
    const newElement = document.createElement('p');
    newElement.textContent = 'New content';
    targetNode.appendChild(newElement);
    targetNode.setAttribute('data-new-attribute', 'newValue');
});
</code></pre>

<p>6. <strong>Stopping Observation</strong> (Optional): To stop observing, call the <code>disconnect</code> method on the observer.</p>
<pre><code>
// observer.disconnect();
</code></pre>

<p>This example demonstrates how to set up a <code>MutationObserver</code> to monitor changes to a DOM element, handle those changes with a callback function, and modify the DOM to trigger observations.</p>
