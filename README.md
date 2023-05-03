Download Link: https://assignmentchef.com/product/solved-cs2030s-problem-set-4
<br>
<ol>

 <li>Consider a generic class A&lt;T&gt; with a type parameter T having a constructor with no argument. Which of the following expressions are valid (with no compilation error) ways of creating a new object of type A? We still consider the expression as valid if the Java compiler produces a warning.

  <ul>

   <li>new A&lt;int&gt;()</li>

   <li>new A&lt;&gt;()</li>

   <li>new A()</li>

  </ul></li>

 <li>In the Java Collections Framework, List is an interface that is implemented by both ArrayList. For each of the statements below, indicate if it is a valid statement with no compilation error. Explain why.

  <ul>

   <li>void foo(List&lt;?&gt; list) { } foo(new ArrayList&lt;String&gt;())</li>

   <li>void foo(List&lt;? super Integer&gt; list) { } foo(new List&lt;Object&gt;())</li>

   <li>void foo(List&lt;? extends Object&gt; list) { } foo(new ArrayList&lt;Object&gt;())</li>

   <li>void foo(List&lt;? super Integer&gt; list) { } foo(new ArrayList&lt;int&gt;())</li>

   <li>void foo(List&lt;? super Integer&gt; list) { } foo(new ArrayList());</li>

  </ul></li>

 <li>In the lecture, we have shown the use of the Comparator&lt;T&gt; interface with the abstract method int compare(T t1, T t2) that returns zero if t1 and t2 are equal, a negative integer if t1 is less than t2, or a positive integer if t2 is less than t1.</li>

</ol>

A generic method T max3(T a, T b, T c, Comparator&lt;T&gt; comp) is defined below. The method takes in three values of type T as well as a Comparator&lt;T&gt;, and returns the maximum among the values.

&lt;T&gt; T max3(T a, T b, T c, Comparator&lt;T&gt; comp) { T max = a;

if (comp.compare(b, max) &gt; 0) { max = b;

}

if (comp.compare(c, max) &gt; 0) { max = c;

} return max;

}

<ul>

 <li>Demonstrate how the max3 method is called to return the maximum of three integers <sup>−</sup>1, 2 and <sup>−</sup></li>

 <li>Other than Comparator&lt;T&gt;, there is a similar Comparable&lt;T&gt; interface with the abstract method int compareTo(T o). This allows one Comparable object to compare itself against another Comparable Now we would like to redefine the max3 method to make use of the Comparable interface instead.</li>

</ul>

&lt;T&gt; T max3(T a, T b, T c) { T max = a;

if (b.compareTo(max) &gt; 0) { max = b;

}

if (c.compareTo(max) &gt; 0) { max = c;

} return max;

}

Does the above method work? What is the compilation error?

(c) Now, we further restrict T to be Comparable&lt;T&gt;

&lt;T extends Comparable&lt;T&gt;&gt; T max3(T a, T b, T c) { T max = a;

if (b.compareTo(max) &gt; 0) { max = b;

}

if (c.compareTo(max) &gt; 0) { max = c;

} return max;

}

Demonstrate how the method max3 can be used to find the maximum of three values −1, 2 and −3. Explain how it works now.

(d) What happens if we replace the method header with each of the following:

<ol>

 <li>&lt;T&gt; Comparable&lt;T&gt; max3(Comparable&lt;T&gt; a, Comparable&lt;T&gt; b, Comparable&lt;T&gt; c)</li>

 <li>&lt;T&gt; T max3 (Comparable&lt;T&gt; a, Comparable&lt;T&gt; b, Comparable&lt;T&gt; c) Comparable max3(Comparable a, Comparable b, Comparable c)</li>

</ol>