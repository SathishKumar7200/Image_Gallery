# Ex.08 Design of Interactive Image Gallery
# DATE : 16-11-2025
## AIM
  To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS

## Step 1:

Clone the github repository and create Django admin interface

## Step 2:

Change settings.py file to allow request from all hosts.

## Step 3:

Use CSS for positioning and styling.

## Step 4:

Write JavaScript program for implementing interactivit

## Step 5:

Validate the HTML and CSS code

## Step 6:

Publish the website in the given URL.

## PROGRAM

```

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Image Gallery</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #090404;
            margin: 0;
            padding: 20px;
            text-align: center;
        }

        .title {
            margin-bottom: 20px;
            font-size: 2rem;
            color: white;
        }

        .gallery {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
        }

        .gallery-img {
            width: 220px;
            height: 150px;
            object-fit: cover;
            border-radius: 6px;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .gallery-img:hover {
            transform: scale(1.05);
        }

        /* Lightbox */
        .lightbox {
            display: none;
            position: fixed;
            z-index: 1000;
            padding-top: 80px;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            background-color: rgba(0,0,0,0.9);
        }

        .lightbox-content {
            margin: auto;
            display: block;
            max-width: 90%;
            max-height: 80%;
            border-radius: 6px;
        }

        .close {
            position: absolute;
            top: 25px;
            right: 40px;
            font-size: 40px;
            color: white;
            cursor: pointer;
        }

        .prev, .next {
            cursor: pointer;
            position: absolute;
            top: 50%;
            font-size: 40px;
            padding: 10px;
            color: white;
            font-weight: bold;
            user-select: none;
        }

        .prev { left: 20px; }
        .next { right: 20px; }

        .prev:hover, .next:hover {
            color: #ffdb4d;
        }
    </style>
</head>
<body>

    <h1 class="title">Interactive Image Gallery</h1>

    <div class="gallery">
        <img src="/static/images/image1.jpg" class="gallery-img">
        <img src="/static/images/image2.jpg" class="gallery-img">
        <img src="/static/images/image3.jpg" class="gallery-img">
        <img src="/static/images/image4.jpg" class="gallery-img">
        <img src="/static/images/image5.jpg" class="gallery-img">
    </div>

    <div id="lightbox" class="lightbox">
        <span class="close">&times;</span>
        <img class="lightbox-content" id="lightbox-img">
        <a class="prev">&#10094;</a>
        <a class="next">&#10095;</a>
    </div>

    <script>
        const galleryImages = document.querySelectorAll(".gallery-img");
        const lightbox = document.getElementById("lightbox");
        const lightboxImg = document.getElementById("lightbox-img");
        const closeBtn = document.querySelector(".close");
        const nextBtn = document.querySelector(".next");
        const prevBtn = document.querySelector(".prev");

        let currentIndex = 0;

        // Open Lightbox
        galleryImages.forEach((img, index) => {
            img.addEventListener("click", () => {
                lightbox.style.display = "block";
                lightboxImg.src = img.src;
                currentIndex = index;
            });
        });

        // Close Lightbox
        closeBtn.onclick = function () {
            lightbox.style.display = "none";
        };

        // Next Image
        nextBtn.onclick = function () {
            currentIndex = (currentIndex + 1) % galleryImages.length;
            lightboxImg.src = galleryImages[currentIndex].src;
        };

        // Previous Image
        prevBtn.onclick = function () {
            currentIndex = (currentIndex - 1 + galleryImages.length) % galleryImages.length;
            lightboxImg.src = galleryImages[currentIndex].src;
        };

        // Close on background click
        lightbox.onclick = function (event) {
            if (event.target === lightbox) {
                lightbox.style.display = "none";
            }
        };
    </script>
</body>
</html>


```


## OUTPUT

![alt text](<Screenshot 2025-11-16 130458.png>)

![alt text](<Screenshot 2025-11-16 130530.png>)

![alt text](<Screenshot 2025-11-16 130547.png>)

![alt text](<Screenshot 2025-11-16 130611.png>)

![alt text](<Screenshot 2025-11-16 130629.png>)

![alt text](<Screenshot 2025-11-16 130644.png>)


## RESULT
  The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
