# BNDL

BNDL is an experimental file format for bundling arbitrary files (images, 3D models, ...) as binary bundle for consumption in JavaScript applications.

## Notes

BNDL is largely a byproduct of the development of [PRWM](https://github.com/kchapelier/PRWM). Support for multiple models in a single file was deliberately not implemented in PRWM as my understanding was that with HTTP/2 it would not matter as requesting multiple files would not incur any additional load time. It was later [pointed out to me](https://github.com/kchapelier/PRWM/issues/3#issuecomment-338487330) by [Alexey Shildyakov](https://github.com/ashl1) that HTTP/2 could still benefit from bundling when dealing with a large number of files. See the [relevant article](https://medium.com/@asyncmax/the-right-way-to-bundle-your-assets-for-faster-sites-over-http-2-437c37efe3ff) for more information.

The BNDL format does not apply any compression on the original file content, so the size of the bundle will usually be about the same as the original files size. It is instead recommended to rely standard HTTP compression (gzip, brotli, ...) when serving BNDL bundles to achieve the best performance.

## Specifications

 * [BNDL version 1 Specifications](https://github.com/kchapelier/BNDL/blob/master/specifications/bndl.md)

## Implementations

### bndl

[github](https://github.com/kchapelier/BNDL/tree/master/implementations/bndl) / [npm](https://www.npmjs.com/package/bndl) / [online example 1](http://www.kchapelier.com/bndl/examples/images.html) / [online example 2](http://www.kchapelier.com/bndl/examples/prwm-models.html)

The reference encoder/decoder for the file format with a CLI tool to generate bundles and an example web loader implementation to consume them in a browser.

## Online tools

### BNDL Inspector

http://www.kchapelier.com/bndl/examples/bndl-inspector.html

Drag and drop a BNDL file to analyze its content.

### BNDL Generator

http://www.kchapelier.com/bndl/examples/bndl-generation.html

Drag and drop files to create a BNDL bundle.

It is recommended to use the CLI tool included in the `bndl` npm package instead.