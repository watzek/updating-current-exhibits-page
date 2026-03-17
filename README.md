# updating-current-exhibits-page
Instructions for updating the current-exhibits page on the special collections website

The Steps:

- Create an item in the private Guide Images collection
- Get the square_thumbnail URL for the image (minus AWS signature)
- Copy all the HTML from the current-exhibits simple page
- Create a sample entry for the new exhibit, and place in the correct spot of the current-exhibits simple page
- Paste back into the simple pages html editor for current-exhibits, and save.



### Step 1 - Create an item with the image, get its square_thumbnail URL

In the Special Collections back end, create an item. The item just needs a title, and add the exhibit image. Add it to the "Guide Images" collection, and make sure it's private. Once saved, click the item link to view its details, and click the image link under "File Metadata".

![guide_image.png](guide_image.png)

Under direct links, click "Square Thumbnail".
![Direct Links](directLinks.png)

In the resulting page displaying the thumbnail, copy the link from the URL bar. It should looks something like this:

https://s3.us-west-2.amazonaws.com/special-collections-digital-collections/square_thumbnails/c409487277a03cc135ae8e932473cfb7.jpg?AWSAccessKeyId=AKIA5SOGV4DPGPTW7EYI&Expires=1773761400&Signature=VnTCfNa6m7k5%2F3uWWYncksc9M1o%3D

We want to get rid of all the URL parameters, so in a text file (or however you want to do it), strip out everything from the "?" forward. The end result should be a stable URL that looks like this:

https://s3.us-west-2.amazonaws.com/special-collections-digital-collections/square_thumbnails/c409487277a03cc135ae8e932473cfb7.jpg

