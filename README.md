# Embed-PDF-in-HTML

Demos embedding PDF files in HTML.

## Use HTML's Elements to Embed a PDF File

1. Use `iframe`. ([online demo](https://tony-xlh.github.io/Embed-PDF-in-HTML/iframe.html))

   ```html
   <iframe src="ddv-sample.pdf" width="100%" height="600px"></iframe>
   ```


2. Use `embed`. ([online demo](https://tony-xlh.github.io/Embed-PDF-in-HTML/embed.html))

   ```html
   <embed src="ddv-sample.pdf" type="application/pdf" width="100%" height="600px" />
   ```
   
3. Use `object`. ([online demo](https://tony-xlh.github.io/Embed-PDF-in-HTML/object.html))

   ```html
   <object data="ddv-sample.pdf" type="application/pdf" width="100%" height="600px">
       <p>Your browser does not support PDFs.
           <a href="ddv-sample.pdf">Download the PDF</a>.
       </p>
   </object>
   ```
   

`iframe` is the recommended way to use. It has the best compatibility.

| Tag         | Recommended   | Support fallback |  issues       |
| ---------- | ------ | ------------- | ---------- |
| `<iframe>` | recommended | no         | will have border by default  |
| `<object>` | more semantic  | yes          | may not work for old and mobile browsers |
| `<embed>`  | Less recommended  | no         | may not work for old browsers  |


On the desktop, the browser's built-in PDF viewer will be used to open the PDF using the three tags. While on the mobile browsers, the behavior varies. On Android, the browsers will give a download link. On iOS, the browsers will render the first page of the PDF.

## Convert the PDF to Images or HTML for Embedding

We can use libraries like Apache PDFBox to convert PDF files to images or use pdf2htmlex to convert them to HTML beforehand to embed the PDF in HTML.

Converting to images produces either blurred text or monster sized files/network cost. Also, text are logically lost, readers cannot perform searching or copying.

Converting to HTML is better. It can make viewing PDF just like viewing a normal web page. But if you need to edit and annotate the PDF, it is not possible. ([the converted version](https://tony-xlh.github.io/Embed-PDF-in-HTML/ddv-sample.html))


## Use PDF JavaScript Libraries to Embed a PDF File

We can use third-party PDF libraries to embed a PDF file. It has the following benefits:

1. We can provide a unified experience for different browsers and platforms.
2. We can customize the user interface.
3. We can use more features like PDF annotation and PDF editing.
4. We can prevent the PDF file from being downloaded for security.


Of course, since the rendering happens on the client side, it has higher requirments for the client.

There are several libraries to use:

1. PDF.js. ([online demo](https://tony-xlh.github.io/Embed-PDF-in-HTML/pdfjs.html))
2. PDFium.js. ([online demo](https://tony-xlh.github.io/Embed-PDF-in-HTML/pdfium.html))

[PDF.js](https://github.com/mozilla/pdf.js/) and [PDFium.js](https://github.com/Jaewoook/pdfium.js/) provides PDF rendering functions, but they do not have a decent viewer.

[Dynamsoft Document Viewer](https://www.dynamsoft.com/document-viewer/overview/) uses PDFium as the engine and provides full-featured UI to view and edit PDFs. It is the more recommended library to use.

[Online demo using Dynamsoft Document Viewer](https://tony-xlh.github.io/Embed-PDF-in-HTML/dynamsoft-document-viewer.html)




