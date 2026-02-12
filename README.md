# Data and Statistics: A Choose Your Own Adventure

An interactive PreTeXt book that teaches data and statistics through a choose-your-own-adventure format. Readers solve problems externally and use their answers to navigate through different learning paths.

## About This Book

This is an educational book built with [PreTeXt](https://pretextbook.org/), an authoring and publishing system for scholarly documents. The book uses a unique choose-your-own-adventure format where:

- Students encounter statistical problems and scenarios
- They work through calculations independently (on paper, calculator, or software)
- Based on their answers, they navigate to different sections
- Each path provides feedback and continues the learning journey

## Structure

The book covers data and statistics topics with interactive branching narratives:
- **Chapter 1: The Beginning of Your Journey** - Introduction to mean and median
- More chapters to be added (missing data, correlation, probability, etc.)

## Prerequisites

To build this book, you need:
- **PreTeXt-CLI**: The PreTeXt command-line interface
- **Python 3.8+**: Required for PreTeXt-CLI
- **LaTeX** (optional): Required only for PDF output

### Installing PreTeXt-CLI

```bash
pip install pretextbook
```

Or using pipx (recommended):
```bash
pipx install pretextbook
```

For more installation options, see the [PreTeXt Guide](https://pretextbook.org/doc/guide/html/ch-installing.html).

## Automated Builds and Deployment

This repository uses GitHub Actions to automatically build and deploy the book:

### Deployment to GitHub Pages

When changes are pushed to the `main` branch, the book is automatically:
1. Built using PreTeXt-CLI
2. Deployed to GitHub Pages

The live book is available at: `https://[username].github.io/choose-your-adventure/`

### Pull Request Validation

When a pull request is opened or updated:
1. The book is built to validate there are no errors
2. Build artifacts are uploaded for review
3. The PR will show a ✅ or ❌ status based on the build result

This ensures all changes are validated before merging.

## Building the Book

### Quick Start

Build the HTML version:
```bash
pretext build web
```

View the HTML output:
```bash
pretext view web
```

This will start a local server and open the book in your browser.

### Building Other Formats

Build PDF (requires LaTeX):
```bash
pretext build print
```

Build EPUB:
```bash
pretext build epub
```

### Available Build Targets

- `web` - HTML for web viewing (default)
- `print` - PDF via LaTeX
- `epub` - EPUB for e-readers

## Project Structure

```
choose-your-adventure/
├── README.md                  # This file
├── project.ptx               # Project configuration
├── source/                   # Source files
│   └── main.ptx             # Main book content
├── publication/              # Publication settings
│   └── publication.ptx      # Output configuration
├── assets/                   # Images and media
│   └── images/              # Image files
├── output/                   # Generated output (not in git)
│   ├── web/                 # HTML output
│   ├── print/               # PDF output
│   └── epub/                # EPUB output
└── generated-assets/         # Auto-generated assets (not in git)
```

## Development Workflow

1. Edit source files in `source/main.ptx`
2. Build the book: `pretext build web`
3. View changes: `pretext view web`
4. Iterate as needed

## Adding Content

The main content is in `source/main.ptx`. The book uses a choose-your-own-adventure structure with:

- **Cross-references** (`<xref ref="section-id"/>`) to link between sections
- **Sections** with unique `xml:id` attributes for linking
- **Interactive choices** presented as lists of cross-references
- **Feedback sections** that guide readers based on their answers

### Example Pattern

```xml
<section xml:id="section-question">
  <title>A Problem</title>
  <p>Calculate the mean of: 2, 4, 6, 8, 10</p>
  <p>
    <ul>
      <li><p>If your answer is 5, go to <xref ref="section-wrong"/></p></li>
      <li><p>If your answer is 6, go to <xref ref="section-correct"/></p></li>
    </ul>
  </p>
</section>

<section xml:id="section-correct">
  <title>Well Done!</title>
  <p>That's correct! The mean is 6.</p>
  <!-- Next challenge -->
</section>
```

## Contributing

To add new content:
1. Add new sections/chapters to `source/main.ptx`
2. Use descriptive `xml:id` attributes
3. Create cross-references to enable navigation
4. Test the build to ensure links work
5. Submit a pull request

## Resources

- [PreTeXt Documentation](https://pretextbook.org/documentation.html)
- [PreTeXt Guide](https://pretextbook.org/doc/guide/html/)
- [PreTeXt Examples](https://pretextbook.org/examples.html)
- [PreTeXt Community](https://groups.google.com/g/pretext-support)

## License

This work is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License. 
To view a copy of this license, visit http://creativecommons.org/licenses/by-sa/4.0/

## Author

[Author information to be added]