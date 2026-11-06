HTML
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Selectors Practice</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header id="main-header">
        <h1 class="title-text">CSS Selectors Practice Page</h1>
        <h2>Understanding Specificity and Cascading</h2>
    </header>

    <main>
        <section class="card">
            <h3>Card 1: Element & Class Selectors</h3>
            <p>This card is styled using the class selector .card.</p>
        </section>

        <section class="card">
            <h3>Card 2: Grouping Selectors</h3>
            <p>Headings h1 and h2 share grouping styles.</p>
        </section>

        <section id="special-card" class="card">
            <h3>Card 3: ID Selector vs Class Selector</h3>
            <p>This specific card tests selector specificity and cascade rules.</p>
        </section>
    </main>
</body>
</html>
CSS
/* style.css */

/* 1. Universal Selector */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

/* 2. Grouping Selector */
h1, h2 {
    font-family: Arial, sans-serif;
    text-align: center;
}

/* 3. Element Selector */
p {
    color: #444444;
    font-size: 1rem;
    line-height: 1.5;
}

/* 4. Class Selector */
.card {
    background-color: #ffffff;
    border: 1px solid #cccccc;
    padding: 20px;
    margin: 15px auto;
    max-width: 500px;
    border-radius: 8px;
}

/* 5. ID Selector */
#main-header {
    background-color: #2c3e50;
    color: #ffffff;
    padding: 20px;
}

/* 6. Conflicting CSS Rules (Cascade and Specificity Demo) */
/* Rule A: Class selector sets background color to white */
.card {
    background-color: #f0f0f0;
}

/* Rule B: ID selector overrides Class selector because ID has higher specificity */
#special-card {
    background-color: #e0f7fa;
    border-color: #00838f;
}
Markdown
# Selector Explanation & Specificity Analysis

1. **Universal Selector (`*`)**: Applied to all elements on the page to reset default margin, padding, and box-sizing.
2. **Grouping Selector (`h1, h2`)**: Applied shared font family and text alignment properties to both `<h1>` and `<h2>` elements.
3. **Element Selector (`p`)**: Directly targeted all paragraph tags to apply consistent text color, font size, and line height.
4. **Class Selector (`.card`)**: Reused across multiple `<section>` tags to give them a consistent card container layout.
5. **ID Selector (`#main-header`)**: Uniquely styled the header section with a distinct background color.
6. **Cascade & Specificity Conflict**: 
   - `.card` attempts to set the background color of `#special-card` to `#f0f0f0`.
   - `#special-card` sets the background color to `#e0f7fa`.
   - **Result**: `#special-card` displays the light blue color (`#e0f7fa`) because an ID selector (`(1,0,0)`) has higher specificity than a class selector (`(0,1,0)`), overriding the class style regardless of order.