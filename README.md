<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Online Code Editor - Sravya</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #1f1f2e;
      color: #fff;
      margin: 0;
      padding: 20px;
    }

    h1, h2 {
      text-align: center;
      color: #58a6ff;
    }

    .editor-container {
      display: flex;
      gap: 10px;
      margin-bottom: 20px;
      flex-wrap: wrap;
    }

    .editor {
      flex: 1;
      min-width: 300px;
      display: flex;
      flex-direction: column;
    }

    textarea {
      height: 200px;
      background: #282c34;
      color: #fff;
      border: 1px solid #444;
      padding: 10px;
      resize: vertical;
      font-family: monospace;
    }

    label {
      margin-bottom: 5px;
      font-weight: bold;
      color: #90caf9;
    }

    iframe {
      width: 100%;
      height: 300px;
      border: 1px solid #444;
      background: white;
    }
  </style>
</head>
<body>
  <h1>Mini Online Code Editor</h1>

  <div class="editor-container">
    <div class="editor">
      <label>HTML</label>
      <textarea id="html-code" placeholder="Write HTML here..."></textarea>
    </div>
    <div class="editor">
      <label>CSS</label>
      <textarea id="css-code" placeholder="Write CSS here..."></textarea>
    </div>
    <div class="editor">
      <label>JavaScript</label>
      <textarea id="js-code" placeholder="Write JavaScript here..."></textarea>
    </div>
  </div>

  <h2>Live Output</h2>
  <iframe id="output"></iframe>

  <script>
    const htmlCode = document.getElementById("html-code");
    const cssCode = document.getElementById("css-code");
    const jsCode = document.getElementById("js-code");
    const output = document.getElementById("output");

    function updateOutput() {
      const html = htmlCode.value;
      const css = `<style>${cssCode.value}</style>`;
      const js = `<script>${jsCode.value}<\/script>`;
      const combined = html + css + js;

      output.srcdoc = combined;
    }

    htmlCode.addEventListener("input", updateOutput);
    cssCode.addEventListener("input", updateOutput);
    jsCode.addEventListener("input", updateOutput);

    // Optional default demo content
    htmlCode.value = "<h2>Hello, Sravya!</h2>";
    cssCode.value = "h2 { color: #58a6ff; text-align: center; }";
    jsCode.value = "console.log('Welcome to your Code Editor!');";

    updateOutput();
  </script>
</body>
</html>
