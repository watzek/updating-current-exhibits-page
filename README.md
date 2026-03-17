# updating-current-exhibits-page
Instructions for updating the current-exhibits page on the special collections website

The Steps:

- Create an item in the private Guide Images collection
- Get the square_thumbnail URL for the image (minus AWS signature)
- Copy all the HTML from the current-exhibits simple page
- Create a sample entry for the new exhibit, and place in the correct spot of the current-exhibits simple page
- Paste back into the simple pages html editor for current-exhibits, and save.



### Step 1 - Create an item with the image, get its square_thumbnail URL

In the Special Collections back end, create an item. The item just needs a title, and add the exhibit image. Add it to the "Guide Images" collection, and make sure it's private. 

![guide_image.png](guide_image.png)

### Step 2 - Get the image URL

Once saved, click the item link to view its details, and click the image link under "File Metadata".

Under direct links, click "Square Thumbnail".
![Direct Links](directLinks.png)

In the resulting page displaying the thumbnail, copy the link from the URL bar. It should looks something like this:

https://s3.us-west-2.amazonaws.com/special-collections-digital-collections/square_thumbnails/c409487277a03cc135ae8e932473cfb7.jpg?AWSAccessKeyId=AKIA5SOGV4DPGPTW7EYI&Expires=1773761400&Signature=VnTCfNa6m7k5%2F3uWWYncksc9M1o%3D

We want to get rid of all the URL parameters, so in a text file (or however you want to do it), strip out everything from the "?" forward. The end result should be a stable URL that looks like this:

https://s3.us-west-2.amazonaws.com/special-collections-digital-collections/square_thumbnails/c409487277a03cc135ae8e932473cfb7.jpg


### Step 3 - Copy all the HTML from the current-exhibits

In the back end, click "Simple Pages" from the admin menu, find Current Exhibits, and click Edit. In the resulting page, click the source code link, and copy all the HTML.

![Current Exhibits](current-exhibits.png)

Since the HTML has no heierarchical indentation, visit an online "pretty printer" (<a href='https://jsonformatter.org/html-pretty-print' target='_blank'>example</a>), paste the code in the left window, and click "Make Pretty". Copy the Pretty HTML, open a code editor (like VS Code), and paste the code in a new file.


### Step 4 - Create a sample entry for the new exhibit

Take a look at the HTML structure of the [current exhibits template](current-exhibit.html). All entries must be contained within:
```
<div class="container w-md-75" style="padding-top: 20px;">

...
</div>
```