<h1>Undefined Behavior and Order of Evaluation in C</h1>

<p>
In C, the order in which function arguments are evaluated is not specified by the C standard. This can lead to undefined behavior, particularly when the arguments involve side effects, such as post-increment operations. Different compilers might handle this evaluation order differently, resulting in varying outputs.
</p>

<h2>The Concept of Undefined Behavior</h2>

<p>
Undefined behavior in C refers to code constructs that the C standard does not define precisely, allowing compilers to interpret and handle them in different ways. One common source of undefined behavior is the order of evaluation of function arguments. When the arguments to a function involve expressions with side effects, such as <code>a++</code>, the final output can vary based on the compiler's implementation.
</p>

<h2>Example of Undefined Behavior</h2>

<p>
Consider the following piece of code:
</p>

<pre><code>
// Interesting piece of code depicting undefined behavior leading to different
// outcomes when compiled with different compilers

#include &lt;stdio.h&gt;

void func (int i, int j) {
    printf("%d $d\n", i, j);
}

int main() {
    int a = 1;
    func(a++, a++);
    printf("%d\n", a);
    return 0;
}
</code></pre>

<p>
In this example, the behavior of <code>func(a++, a++)</code> is undefined because the C standard does not specify the order in which function arguments are evaluated. As a result, different compilers might produce different outputs.
</p>

<h2>Compiler-Specific Behavior</h2>

<p>
Different compilers, like Apple Clang and GNU GCC, may evaluate function arguments in different orders, leading to varying outputs. This variability is due to how each compiler implements the evaluation of function arguments with side effects.
</p>

<ul>
    <li>Apple Clang might produce: <pre><code>1 $d\n3</code></pre></li>
    <li>GNU GCC might produce: <pre><code>2 $d\n3</code></pre></li>
</ul>

<h3>Explanation</h3>

<p>
The reason for this might be that GCC evaluates <code>a++</code> for the second argument (<code>j</code>) before evaluating <code>a++</code> for the first argument (<code>i</code>). Conversely, Clang might evaluate <code>a++</code> for the first argument (<code>i</code>) before evaluating <code>a++</code> for the second argument (<code>j</code>). Since the C standard does not specify the order of evaluation, both behaviors are valid according to the standard.
</p>

<p>
Here is a detailed explanation of the outputs:
</p>

<ul>
    <li>
        <strong>Apple Clang:</strong>
        <p>
        Clang might evaluate the first <code>a++</code> before the second <code>a++</code>. Therefore, <code>i</code> gets the original value of <code>a</code> (which is <code>1</code>), and <code>j</code> gets the incremented value of <code>a</code> (which is <code>2</code>). After the function call, <code>a</code> is incremented to <code>3</code>.
        </p>
    </li>
    <li>
        <strong>GNU GCC:</strong>
        <p>
        GCC might evaluate the second <code>a++</code> before the first <code>a++</code>. As a result, <code>j</code> gets the original value of <code>a</code> (which is <code>1</code>), and <code>i</code> gets the incremented value of <code>a</code> (which is <code>2</code>). After the function call, <code>a</code> is incremented to <code>3</code>.
        </p>
    </li>
</ul>

<p>
I hope this helps clarify your query.
</p>
