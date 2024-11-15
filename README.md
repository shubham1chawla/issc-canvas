# ISSC Canvas Courses

This repository contains files for the ISSC's Canvas courses.

## How to setup & maintain Canvas course

The following sections discuss how to create and manage Canvas courses. Please look at the table of contents to jump to a specific section.

- [Uploading files to Canvas](#uploading-files-to-canvas)
- [Linking images in HTML files](#linking-images-in-html-files)
- [Adding HTML-based pages to Canvas](#adding-html-based-pages-to-canvas)

### Uploading files to Canvas

![Canvas Files Tab](https://github.com/user-attachments/assets/1e88c24d-3212-47b3-a590-d2870a4b01fc)

1. Navigate to the Canvas course's `files` section. The URL for it will be `https://canvas.asu.edu/courses/<COURSE_ID>/files`.
2. Create new folders to organize the content based on the file type.

> [!NOTE]
> Previous Canvas courses had a folder called `html` for `.html` and `.css` files. For images, they had a folder called `images`.

3. Once in the folder, you can upload multiple files that need to be in that folder.

![Publish Button](https://github.com/user-attachments/assets/fc5de266-2f47-46b6-b206-b8d6fbf70896)

![Set visibility to Public](https://github.com/user-attachments/assets/388d4e27-9ba1-48bf-be80-d81d4077cca4)

4. By default, the files will have the visibility set to `Inherit from Course`; change it to `Public` to allow Canvas app users to access them.
5. You can now use this file in the Canvas course using its ID.
6. To retrieve the file ID, click on the uploaded file, and it will open it in a pop-up preview. The number following `preview=` in the URL is the file ID.

### Linking images in HTML files
1. Upload the image to Canvas files and copy the image's file ID (refer to the _Uploading files to Canvas_)
2. You can add an image to the HTML file using the following code snippet -

```html
<img class="..." alt="..." src="https://canvas.asu.edu/courses/<COURSE_ID>/files/<FILE_ID>/preview" />
```

### Adding HTML-based pages to Canvas
1. Upload the HTML file to Canvas files and copy its file ID (refer to the _Uploading files to Canvas_)
2. Create an empty page on Canvas and add it to whatever module you'd like.

![Switch to HTML editor](https://github.com/user-attachments/assets/814c4d1f-918e-4988-b8d3-25b626ff4b7d)

3. Edit the page and switch to HTML editor mode.
4. Paste the following snippet in the HTML editor to link your uploaded HTML files to this page.

```html
<div>
  <iframe
    style="max-width: 100%; width: 1000px; height: 3000px; overflow: hidden;"
    src="https://canvas.asu.edu/courses/<COURSE_ID>/files/<FILE_ID>/preview"
    data-api-endpoint="https://canvas.asu.edu/api/v1/courses/<COURSE_ID>/files/<FILE_ID"
    data-api-returntype="File">
  </iframe>
</div>
```

5. Update the snippet with `COURSE_ID` and `FILE_ID`.

> [!TIP]
> You may need to change the height according to the content on your HTML page. You will see a scroll bar if you keep the height too low. However, if you keep it too high, you will see the page taking up too much space.
