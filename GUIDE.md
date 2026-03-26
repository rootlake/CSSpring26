# MathSciGraphs: Teacher Guide

## LLM Image Generation vs Code-Based Graphs

### LLM image generation (DALL-E, Midjourney, etc.)

- **One-off**: Each image is unique; regenerating yields different results
- **Hard to edit**: Can't tweak axes, data, or labels without starting over
- **No data fidelity**: Models approximate; numbers and curves may be wrong
- **Use case**: Illustrations, concept art, rough sketches

### Code-based graphs (AI-assisted)

- **Editable**: Change the equation, data, or styling in code
- **Reproducible**: Same input always yields same output
- **Data-accurate**: Libraries compute correct values
- **Use case**: Teaching, assessments, presentations, worksheets

---

## Workflow

1. Describe the graph you want in Cursor chat
2. AI generates HTML/JS code
3. Save as `graphs/XX-name.html`
4. Open in browser (double-click or `open graphs/01-function-plot.html`)

---

## Prompt Keywords by Graph Type

| Graph Type | Library | Example prompt |
|------------|---------|----------------|
| Function plot (y = f(x)) | Plotly.js | "Use Plotly.js to plot y = x² − 2x − 3 from -5 to 5" |
| Parametric curve | Plotly.js | "Use Plotly.js to plot x = 3cos(t), y = 2sin(t) for t in [0, 2π]" |
| Polar plot | Plotly.js | "Use Plotly.js to make a polar plot of r = 2cos(3θ)" |
| Bar chart | Chart.js | "Use Chart.js to make a bar chart of [22, 19, 18, 21, 24]" |
| Scatter plot | Plotly.js or Chart.js | "Use Plotly.js scatter plot with these x,y points" |
| Histogram | Plotly.js | "Use Plotly.js histogram of this data" |
| Vector diagram | D3.js | "Use D3.js to draw force vectors F₁ and F₂ from origin" |
| Free-body diagram | D3.js or SVG | "Use D3.js free-body diagram with N, W, F, and friction" |
| Circuit diagram | D3.js or SVG | "Use D3.js to draw a simple series circuit with battery and resistor" |
| Phase diagram | Plotly.js | "Use Plotly.js to draw a water phase diagram (P vs T)" |

### Key library names to include in prompts

- **Plotly.js** — function plots, parametric, polar, scatter, histogram, phase diagrams
- **Chart.js** — bar, line, pie, radar (simpler API, fewer math types)
- **D3.js** — vectors, diagrams, custom SVG (more control, steeper learning curve)

---

## When to Use Python Instead

Use Python when you need:

- Symbolic math (SymPy for derivatives, integrals)
- ODEs or simulations (scipy)
- Heavy computation before plotting

**Workflow**: Write Python script → `fig.write_html('output.html')` (Plotly) or export SVG (matplotlib) → open HTML in browser. Viewers still only need the HTML file.

---

## Copy-Paste Prompt Templates

**Function plot**
> Use Plotly.js in a standalone HTML file to plot [equation] from [xmin] to [xmax]. Full viewport, CDN only.

**Bar chart**
> Use Chart.js in a standalone HTML file to make a bar chart with labels [X] and data [Y]. Full viewport, CDN only.

**Vector diagram**
> Use D3.js in a standalone HTML file to draw vectors [describe]. Arrowheads, labels, origin at center. Full viewport, CDN only.

**Polar plot**
> Use Plotly.js scatterpolar to plot r = [equation in θ]. Full viewport, CDN only.
