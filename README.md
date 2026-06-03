# Markdown Reference Converter

A small, dependency-free web app that converts Markdown reference-style links into inline links and appends a readable references section.

## Features

- Converts reference-style links such as `[label][id]` and collapsed references such as `[label][]`.
- Leaves unresolved references unchanged.
- Converts reference-style images such as `![alt][id]` into inline images such as `![alt](URL "title")`.
- Removes `utm_source` query parameters from converted URLs.
- Appends a references section using a customizable heading.
- Supports dark, light, and system theme modes.
- Runs entirely in the browser with no build step or server-side processing.

## Usage

1. Open `public/index.html` in a web browser.
2. Paste or type Markdown into the **Input Markdown** field.
3. Optionally edit the references heading text.
4. Select **Convert**.
5. Copy the converted Markdown from the **Output Markdown** field.

## Example

Input:

```markdown
Read the [project docs][docs] for more information.

[docs]: https://example.com/docs?utm_source=newsletter "Documentation"
```

Output:

```markdown
Read the [docs](https://example.com/docs "project docs: Documentation https://example.com/docs") for more information.

## References
- (docs) Documentation [https://example.com/docs](https://example.com/docs)
```

## Notes and limitations

- Multi-line reference definitions are not supported.
- Inline links are not transformed.
- Reference-style images are converted when their reference definitions are available.
- Existing references-heading detection is case-sensitive.

## Development

This project is a static HTML, CSS, and JavaScript app. No dependencies are required.

To run it locally, serve the `public` directory with any static file server, for example:

```sh
python3 -m http.server 8000 -d public
```

Then open <http://localhost:8000>.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
