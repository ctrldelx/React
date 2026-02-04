# ReactJS Basics (LMS-Style)

> **Course:** ReactJS for Beginners  \
> **Module 1:** Getting Started  \
> **Lesson 1:** What is React?

<style>
  :root {
    --bg: #0b1220;
    --surface: #111827;
    --card: #0f172a;
    --text: #e5e7eb;
    --muted: #94a3b8;
    --primary: #38bdf8;
    --accent: #a78bfa;
    --success: #22c55e;
    --warning: #f59e0b;
  }

  .lms {
    font-family: "Inter", system-ui, -apple-system, sans-serif;
    color: var(--text);
    background: linear-gradient(135deg, var(--bg), #050816 70%);
    border-radius: 16px;
    padding: 24px;
    margin: 16px 0 32px;
    box-shadow: 0 20px 40px rgba(2, 6, 23, 0.4);
  }

  .lms-header {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 24px;
  }

  .lms-title {
    display: flex;
    flex-direction: column;
    gap: 6px;
  }

  .lms-title h2 {
    margin: 0;
    font-size: clamp(1.4rem, 2vw + 1rem, 2.2rem);
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 6px 12px;
    border-radius: 999px;
    background: rgba(56, 189, 248, 0.15);
    color: var(--primary);
    font-size: 0.85rem;
    font-weight: 600;
    letter-spacing: 0.02em;
  }

  .progress {
    flex: 1 1 200px;
    min-width: 200px;
  }

  .progress-bar {
    height: 10px;
    background: rgba(148, 163, 184, 0.2);
    border-radius: 999px;
    overflow: hidden;
  }

  .progress-fill {
    height: 100%;
    width: 25%;
    background: linear-gradient(90deg, var(--primary), var(--accent));
    animation: fill 1.8s ease-out;
  }

  .progress-meta {
    display: flex;
    justify-content: space-between;
    font-size: 0.8rem;
    color: var(--muted);
    margin-top: 6px;
  }

  .grid {
    display: grid;
    gap: 16px;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  }

  .card {
    background: var(--card);
    border-radius: 14px;
    padding: 16px;
    border: 1px solid rgba(148, 163, 184, 0.15);
    animation: float-in 0.8s ease forwards;
    opacity: 0;
  }

  .card:nth-child(1) { animation-delay: 0.05s; }
  .card:nth-child(2) { animation-delay: 0.1s; }
  .card:nth-child(3) { animation-delay: 0.15s; }
  .card:nth-child(4) { animation-delay: 0.2s; }

  .card h3 {
    margin-top: 0;
    color: var(--primary);
  }

  .steps {
    display: grid;
    gap: 12px;
  }

  .step {
    display: flex;
    gap: 12px;
    align-items: flex-start;
    padding: 12px;
    border-radius: 12px;
    background: rgba(15, 23, 42, 0.7);
    border: 1px solid rgba(148, 163, 184, 0.15);
    animation: pulse 2.6s ease-in-out infinite;
  }

  .step-icon {
    width: 32px;
    height: 32px;
    border-radius: 8px;
    background: rgba(34, 197, 94, 0.2);
    color: var(--success);
    display: grid;
    place-items: center;
    font-weight: 700;
  }

  .lesson-footer {
    margin-top: 24px;
    padding: 16px;
    border-radius: 14px;
    background: rgba(167, 139, 250, 0.12);
    border: 1px solid rgba(167, 139, 250, 0.3);
  }

  .quiz {
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin-top: 8px;
  }

  .quiz span {
    color: var(--warning);
    font-weight: 600;
  }

  @keyframes float-in {
    from { transform: translateY(12px); opacity: 0; }
    to { transform: translateY(0); opacity: 1; }
  }

  @keyframes fill {
    from { width: 0%; }
    to { width: 25%; }
  }

  @keyframes pulse {
    0%, 100% { box-shadow: 0 0 0 rgba(56, 189, 248, 0); }
    50% { box-shadow: 0 0 12px rgba(56, 189, 248, 0.4); }
  }

  @media (max-width: 720px) {
    .lms { padding: 18px; }
    .lms-header { flex-direction: column; align-items: flex-start; }
    .progress { width: 100%; }
  }
</style>

<div class="lms">
  <div class="lms-header">
    <div class="lms-title">
      <span class="badge">Lesson 1 · Foundations</span>
      <h2>React in Plain Words</h2>
      <div style="color: var(--muted);">Estimated time: 8 minutes · Level: Beginner</div>
    </div>
    <div class="progress">
      <div class="progress-bar">
        <div class="progress-fill"></div>
      </div>
      <div class="progress-meta">
        <span>Course progress</span>
        <span>1 / 4 lessons</span>
      </div>
    </div>
  </div>

  <div class="grid">
    <div class="card">
      <h3>✅ Goal</h3>
      <p>Understand what React is, why it exists, and how it breaks a page into small reusable parts called <strong>components</strong>.</p>
    </div>
    <div class="card">
      <h3>💡 What is React?</h3>
      <p>React is a JavaScript library for building user interfaces. You describe the UI, and React keeps it updated for you.</p>
    </div>
    <div class="card">
      <h3>🚀 Why use it?</h3>
      <ul>
        <li><strong>Reusable pieces:</strong> Build a button once, use it everywhere.</li>
        <li><strong>Clear structure:</strong> UI is organized into components.</li>
        <li><strong>Fast updates:</strong> React updates only what changed.</li>
      </ul>
    </div>
    <div class="card">
      <h3>🧩 Core idea</h3>
      <p>A page is just a tree of components. For example: <em>Header</em>, <em>Sidebar</em>, <em>ProductList</em>.</p>
    </div>
  </div>

  <h3 style="margin-top: 24px;">Step-by-step model</h3>
  <div class="steps">
    <div class="step">
      <div class="step-icon">1</div>
      <div>
        <strong>Input:</strong> Data goes into a component (props + state).
      </div>
    </div>
    <div class="step">
      <div class="step-icon">2</div>
      <div>
        <strong>Render:</strong> The component returns what the UI should look like.
      </div>
    </div>
    <div class="step">
      <div class="step-icon">3</div>
      <div>
        <strong>Update:</strong> When data changes, React re-renders the UI automatically.
      </div>
    </div>
  </div>

  <div class="lesson-footer">
    <strong>Mini-practice (2 minutes)</strong>
    <p>List 3 UI parts of any website you use daily. Example: Search bar, profile menu, product card. These are components.</p>
    <div class="quiz">
      <span>Quick check</span>
      <div><strong>Q:</strong> What is the main building block in React?</div>
      <div><strong>A:</strong> A component.</div>
    </div>
  </div>
</div>

---

## Next lesson
We’ll build your first React component and render it to the page.

---

# Lesson 2: Your First Component (Hands-on)

> **Module 1:** Getting Started  \
> **Lesson 2:** Create a simple component

<div class="lms">
  <div class="lms-header">
    <div class="lms-title">
      <span class="badge">Lesson 2 · Practice</span>
      <h2>Build a Hello Component</h2>
      <div style="color: var(--muted);">Estimated time: 10 minutes · Level: Beginner</div>
    </div>
    <div class="progress">
      <div class="progress-bar">
        <div class="progress-fill" style="width: 50%;"></div>
      </div>
      <div class="progress-meta">
        <span>Course progress</span>
        <span>2 / 4 lessons</span>
      </div>
    </div>
  </div>

  <div class="grid">
    <div class="card">
      <h3>✅ Goal</h3>
      <p>Create a simple React component and show it on the page.</p>
    </div>
    <div class="card">
      <h3>🧠 Remember</h3>
      <p>A component is just a JavaScript function that returns UI.</p>
    </div>
    <div class="card">
      <h3>🧩 Example</h3>
      <pre><code>function Hello() {
  return &lt;h1&gt;Hello React!&lt;/h1&gt;;
}</code></pre>
    </div>
    <div class="card">
      <h3>✨ Result</h3>
      <p>When React renders <strong>Hello</strong>, the page shows “Hello React!”</p>
    </div>
  </div>

  <h3 style="margin-top: 24px;">Step-by-step build</h3>
  <div class="steps">
    <div class="step">
      <div class="step-icon">1</div>
      <div>
        <strong>Create a component:</strong> Write a function that returns JSX.
      </div>
    </div>
    <div class="step">
      <div class="step-icon">2</div>
      <div>
        <strong>Render it:</strong> Use it like an HTML tag: <code>&lt;Hello /&gt;</code>.
      </div>
    </div>
    <div class="step">
      <div class="step-icon">3</div>
      <div>
        <strong>See it:</strong> The browser shows the UI returned by your component.
      </div>
    </div>
  </div>

  <div class="lesson-footer">
    <strong>Mini-practice (3 minutes)</strong>
    <p>Change the text to your name, e.g. “Hello Amina!” Then add a second line: “Welcome to React.”</p>
    <div class="quiz">
      <span>Quick check</span>
      <div><strong>Q:</strong> What does a React component return?</div>
      <div><strong>A:</strong> UI (JSX).</div>
    </div>
  </div>
</div>

---

## Next lesson
We’ll pass data into components using <strong>props</strong>.

---

# Lesson 3: Passing Data with Props

> **Module 1:** Getting Started  \
> **Lesson 3:** Reuse components with data

<div class="lms">
  <div class="lms-header">
    <div class="lms-title">
      <span class="badge">Lesson 3 · Props</span>
      <h2>Make Components Dynamic</h2>
      <div style="color: var(--muted);">Estimated time: 12 minutes · Level: Beginner</div>
    </div>
    <div class="progress">
      <div class="progress-bar">
        <div class="progress-fill" style="width: 75%;"></div>
      </div>
      <div class="progress-meta">
        <span>Course progress</span>
        <span>3 / 4 lessons</span>
      </div>
    </div>
  </div>

  <div class="grid">
    <div class="card">
      <h3>✅ Goal</h3>
      <p>Learn how to pass data into components so one component can show different content.</p>
    </div>
    <div class="card">
      <h3>📦 What are props?</h3>
      <p>Props are inputs to a component. Think of them like arguments you pass to a function.</p>
    </div>
    <div class="card">
      <h3>🧩 Example</h3>
      <pre><code>function Greeting(props) {
  return &lt;h2&gt;Hello {props.name}!&lt;/h2&gt;;
}

// Usage:
&lt;Greeting name=\"Amina\" /&gt;</code></pre>
    </div>
    <div class="card">
      <h3>✨ Result</h3>
      <p>React renders: <strong>Hello Amina!</strong> Change the name prop and the text updates.</p>
    </div>
  </div>

  <h3 style="margin-top: 24px;">Step-by-step</h3>
  <div class="steps">
    <div class="step">
      <div class="step-icon">1</div>
      <div>
        <strong>Add a prop:</strong> Put a value on your component like <code>name=\"Amina\"</code>.
      </div>
    </div>
    <div class="step">
      <div class="step-icon">2</div>
      <div>
        <strong>Read it:</strong> Use <code>props.name</code> inside the component.
      </div>
    </div>
    <div class="step">
      <div class="step-icon">3</div>
      <div>
        <strong>Reuse it:</strong> Render <code>&lt;Greeting /&gt;</code> for multiple names.
      </div>
    </div>
  </div>

  <div class="lesson-footer">
    <strong>Mini-practice (4 minutes)</strong>
    <p>Create a <code>Badge</code> component that takes <code>label</code> and <code>color</code> props, then render three badges.</p>
    <div class="quiz">
      <span>Quick check</span>
      <div><strong>Q:</strong> What are props in React?</div>
      <div><strong>A:</strong> Inputs passed into a component.</div>
    </div>
  </div>
</div>

---

## Next lesson
We’ll learn about <strong>state</strong> and how to update the UI on user actions.

---

# Lesson 4: State (Make UI Interactive)

> **Module 1:** Getting Started  \
> **Lesson 4:** Update the UI with state

<div class="lms">
  <div class="lms-header">
    <div class="lms-title">
      <span class="badge">Lesson 4 · State</span>
      <h2>UI That Responds to Clicks</h2>
      <div style="color: var(--muted);">Estimated time: 15 minutes · Level: Beginner</div>
    </div>
    <div class="progress">
      <div class="progress-bar">
        <div class="progress-fill" style="width: 100%;"></div>
      </div>
      <div class="progress-meta">
        <span>Course progress</span>
        <span>4 / 4 lessons</span>
      </div>
    </div>
  </div>

  <div class="grid">
    <div class="card">
      <h3>✅ Goal</h3>
      <p>Learn how to store changing data with <strong>state</strong> and update the UI when a user clicks.</p>
    </div>
    <div class="card">
      <h3>🧠 What is state?</h3>
      <p>State is data that can change over time, like a counter or form input.</p>
    </div>
    <div class="card">
      <h3>🧩 Example</h3>
      <pre><code>import { useState } from \"react\";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    &lt;div&gt;
      &lt;p&gt;Count: {count}&lt;/p&gt;
      &lt;button onClick={() =&gt; setCount(count + 1)}&gt;
        Add 1
      &lt;/button&gt;
    &lt;/div&gt;
  );
}</code></pre>
    </div>
    <div class="card">
      <h3>✨ Result</h3>
      <p>Each click updates <strong>count</strong>, and React re-renders the new number.</p>
    </div>
  </div>

  <h3 style="margin-top: 24px;">Step-by-step</h3>
  <div class="steps">
    <div class="step">
      <div class="step-icon">1</div>
      <div>
        <strong>Create state:</strong> <code>const [count, setCount] = useState(0);</code>
      </div>
    </div>
    <div class="step">
      <div class="step-icon">2</div>
      <div>
        <strong>Show it:</strong> Render <code>{count}</code> in your UI.
      </div>
    </div>
    <div class="step">
      <div class="step-icon">3</div>
      <div>
        <strong>Update it:</strong> Call <code>setCount</code> on a button click.
      </div>
    </div>
  </div>

  <div class="lesson-footer">
    <strong>Mini-practice (5 minutes)</strong>
    <p>Build a <code>LikeButton</code> that starts at 0 and increases each time you click.</p>
    <div class="quiz">
      <span>Quick check</span>
      <div><strong>Q:</strong> What does <code>useState</code> return?</div>
      <div><strong>A:</strong> A value and a function to update it.</div>
    </div>
  </div>
</div>

---

## Next lesson
You’ve completed Module 1! Next, we can build a small project using everything above.
