# ComPDF SDK for Web (Next.js Example)

As part of the KDAN ecosystem, [ComPDF SDK for Web](https://www.compdf.com/web?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs) is a powerful JavaScript-based PDF library that enables developers to easily add PDF viewing, annotation, editing, and more to their applications across multiple frameworks including [Vanilla JavaScript](https://www.compdf.com/guides/pdf-sdk/web/make-a-program#integrate-into-a-vanilla-javascript-project?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs), [Vue.js](https://www.compdf.com/guides/pdf-sdk/web/frameworks/vue?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs), [React](https://www.compdf.com/guides/pdf-sdk/web/frameworks/react?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs), [Angular](https://www.compdf.com/guides/pdf-sdk/web/frameworks/angular?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs), [Next.js](https://www.compdf.com/guides/pdf-sdk/web/frameworks/nextjs?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs), [Nuxt.js](https://www.compdf.com/guides/pdf-sdk/web/frameworks/nuxtjs?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs), and more — with just a few lines of code.

> If you find this library helpful, please consider giving us a ⭐ **Star** on GitHub! Have feedback or questions? Join the conversation in our [Discussions](https://github.com/ComPDFKit/compdfkit-web-example-nextjs/discussions).

![webui](https://www.compdf.com/images/platform/web/webDemo@2x.png)

**Why ComPDF SDK?**

* **Easy to Integrate**: Clear docs and a powerful JavaScript API let you add PDF features in just a few lines of code.

* **Fully Customizable UI**: Ship your own look and feel with source-level control over every UI element.

* **Comprehensive PDF Features**: View, annotate, edit, convert, OCR, redact, sign, compress, compare, and more — all in one SDK.

* **5×24 Expert Support**: One-to-one technical assistance via email, phone, and on-site service.

## Table of Contents

- [Supported Features](#supported-features)
- [How to Make a Next.js PDF Viewer App](#how-to-make-a-nextjs-pdf-viewer-app)
- [Free Trial and License](#free-trial-and-license)
- [Changelog](#changelog)
- [Support](#support)
- [Note](#note)
- [Related](#related)

## Supported Features

* **Viewer**: 
  
  - Fast and smooth PDF rendering and viewing
  * Display Modes - single/double page, vertical & horizontal scrolling, cover mode, crop mode
  * Text Search & Selection
  * PDF Navigation - outlines, bookmarks

* **Annotations**:
  
  * Notes - add longer comments with adjustable icon shape and color
  
  * Ink - freehand drawing with customizable color, opacity, line thickness
  
  * Text - add, move, resize text directly on page
  
  * Inspector - adjust annotation looks (line styles, borders, colors, opacity, font)
  
  * Comment on Annotations and Update Status
  
  * Import & Export & Flatten Annotations (XFDF, FDF, JSON)
  
  * Highlight, Underline, Strikeout, Squiggly
  
  * Shapes - Rectangle, Oval, Line, Arrow, Polygon, Polyline, Cloud
  
  * Stamps, Sound, Movie, File Attachment, Link, Distance, Perimeter, Area

* **Document Editor**: 
  
  - Page manipulation - insert, delete, rotate, reorder, extract, crop
  * Split PDF, Merge PDF

* **Content Editor**: Edit PDF text and images directly like in Word

* **Signatures**: 
  
  - Electronic Signatures - draw, type, image signatures
  * Digital Signatures - certificate-based signature validation

* **Forms**: 
  
  - Process fillable and static PDF forms
  * Form filling, form creation, form flattening

* **Security**: 
  
  - Encryption - set open password, permission password
  * Restrict printing, copying, editing

* **Redaction**: Permanently remove sensitive content from PDFs

* **Layers**: View, edit, display, lock, and export specific layers within a file

* **Color Separation**: Identify color models like CMYK, PMS. Toggle color visibility and view details.

* **Measurement**: Distance, area, perimeter measurement tools

* **Compare Documents**: Side-by-side document comparison to highlight differences

## How to Make a Next.js PDF Viewer App

### Prerequisites

- The latest stable version of Node.js.
- A package manager compatible with npm.
- Apply the License Key: Contact [ComPDFKit's sales team](https://www.compdf.com/contact-sales?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs) to get a free 30-day license to test the project.

### Create a New Project

Create a new Next.js project:

```bash
npx create-next-app@latest
cd compdfkit-app
```

During setup, Next.js will prompt you with a series of questions. For this example, choose the default options.

### Add ComPDF for Web

1. Install the webviewer package:

```bash
npm i @compdfkit_pdf_sdk/webviewer --save
```

2. Copy the static resource files to your project's public folder:

```bash
cp -a ./node_modules/@compdfkit_pdf_sdk/webviewer/dist/. ./public/webviewer
```

### Display a PDF

1. Add your PDF document to the `public/webviewer/example` directory.

2. If you chose JavaScript during setup, add the following code to your `app/page.js` file:

```javascript
'use client';
import React, { useRef, useEffect } from 'react';
import Head from 'next/head'
import Webviewer from '@compdfkit_pdf_sdk/webviewer';

export default function Home() {
  const viewer = useRef(null);
  let docViewer = null;

  useEffect(() => {
    Webviewer.init({
      path: '/',
      pdfUrl: './example/developer_guide_web.pdf',
      license: '<Input your license here>',
    }, viewer.current).then((instance) => {
      docViewer = instance.docViewer;
      docViewer.addEvent('documentloaded', async () => {
        console.log('ComPDFKit Web Demo loaded');
      })
    })
  });

  return (
    <>
      <Head>
        <title>ComPDFKit Web Viewer</title>
        <meta name="description" content="Generated by create next app" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <link rel="icon" href="/favicon.ico" />
      </Head>
      <div id="webviewer" ref={viewer} style={{ height: '100vh', overflow: 'hidden' }}></div>
    </>
  )
}
```

### Run the App

```bash
npm run dev
```

Open `http://localhost:3000` on your browser.

## Free Trial and License

Replace the `<Input your license here>` field in the `app/page.js` with the license you get from our Team.

ComPDF SDK for Web supports flexible licensing options. You can [apply for a license online](https://www.compdf.com/pricing?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs) to use it, reducing the process of contacting the service team and saving you time. If you need more information, you can [contact our sales team](https://www.compdf.com/contact-sales?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs). Each license is valid only for the root domain name and any of its subdomains. 

> *The license we provide on Github can only run the demo. If you want to integrate our Web PDF SDK into your own Next.js project, please [apply for a free trial license](https://www.compdf.com/pricing?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs) on the website.*

Please note that it is not allowed to distribute any documents, sample code, or source code from the ComPDF SDK package to third parties.

## Changelog

Go to our [changelog](https://www.compdf.com/pdf-sdk/changelog-web?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs) to keep up with the latest updates, improvements, and bug fixes.

## Support

ComPDF has a professional R&D team that produces comprehensive technical documentation and guides to help developers. Also, you can get an immediate response when reporting your problems to our support team.

- For detailed information, please visit our [Guides](https://www.compdf.com/guides/pdf-sdk/web/overview?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs) page.

- For technical assistance, please reach out to our [Technical Support](https://www.compdf.com/support?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs).

- To get more details and an accurate quote, please contact our [Sales Team](https://compdf.com/contact-sales?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs).

## Note

We are glad to announce that you can register a ComPDF API account for a [free trial](https://api.compdf.com/api/pricing?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs) to process 200+ API calls per month for free.

## Related

* Download [ComPDF SDK for Web](https://www.npmjs.com/package/@compdfkit_pdf_sdk/webviewer) in npm.

* [Online Demo of ComPDF SDK](https://www.compdf.com/webviewer/demo?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs)

* Integrate ComPDF SDK for Web into [Salesforce](https://www.compdf.com/pdf-sdk/salesforce?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs), [SharePoint](https://www.compdf.com/pdf-sdk/sharepoint?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs), [Microsoft Teams](https://www.compdf.com/contact-sales?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs), etc.

* [Next.js Tutorial: Build Next.js Web PDF Viewer](https://www.compdf.com/blog/next.js-tutorial-build-web-pdf-viewer?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs)

* [ComPDF SDK for Web - Standalone Deployment](https://www.compdf.com/blog/compdfkit-standalone-deployment-for-web?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs)

* Recognize and extract data from PDFs with our online [Extract Demo](https://www.compdf.com/pdf-extract/demo?utm_source=github_readme_web_example_nextjs&utm_medium=referral&utm_campaign=github_readme_web_example_nextjs)
