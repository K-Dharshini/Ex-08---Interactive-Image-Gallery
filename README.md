# Ex-08---Interactive-Image-Gallery

## Date:

## AIM:
To design, develop, and deploy an interactive web application for browsing an image gallery with JavaScript interactions.

## DESIGN STEPS:

### Step 1:
Create a new frame in Figma.

### Step 2: 
Choose a preset size based on the gallery layout.

### Step 3:
Select grid or list shapes for displaying images.

### Step 4: 
Import images to populate the gallery.

### Step 5: 
Implement JavaScript for hover effects, image detail view, and zoom.

### Step 6:
Validate the HTML, CSS, and JavaScript code.

### Step 7: 
Publish the website on the assigned URL.

## PROGRAM:

~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dog Lover's Paradise</title>
    <link rel="stylesheet" href="T.css">
    <style>
        /* Add basic styles for the gallery */
        .gallery {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
        }
        .dog {
            position: relative;
            width: 200px;
            cursor: pointer;
        }
        .dog img {
            width: 100%;
            border-radius: 8px;
            transition: transform 0.3s ease-in-out, opacity 0.3s ease;
        }
        .dog img:hover {
            transform: scale(1.1);
            opacity: 0.8;
        }
        /* Lightbox styling */
        .lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            align-items: center;
            justify-content: center;
        }
        .lightbox img {
            max-width: 90%;
            max-height: 90%;
            border-radius: 8px;
        }
        .lightbox:target {
            display: flex;
        }
        .lightbox .close {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 30px;
            color: white;
            cursor: pointer;
            background: rgba(0, 0, 0, 0.5);
            border-radius: 50%;
            padding: 5px;
        }

        /* Watermark styling */
        .watermark {
            position: fixed;
            font-size: 72px;
            color: rgba(0, 0, 0, 0.2);  /* Black color with transparency */
            z-index: -1;  /* Ensure it's behind other content */
            pointer-events: none;  /* Prevents watermark from interfering with interactions */
            white-space: nowrap;
            transform: rotate(-45deg); /* Rotate the watermark */
        }

        /* Specific positions for each watermark */
        .watermark-1 {
            top: 20%;  /* Position the first watermark */
            left: 10%;
        }

        .watermark-2 {
            top: 50%;  /* Position the second watermark */
            left: 40%;
        }

        .watermark-3 {
            top: 70%;  /* Position the third watermark */
            left: 70%;
        }

        .watermark-4 {
            top: 80%;  /* Position the fourth watermark */
            left: 80%;
        }
    </style>
</head>
<body>
    <header>
        <div class="header-content">
            <h1>Welcome to Dog Lover's Paradise</h1>
            <p>Your go-to place for all things dog!</p>
            <p>Done by: Dharshini K - 21222320047</p>
        </div>
    </header>
    <main>
        <section class="gallery">
            <div class="dog" onclick="openLightbox('img1')">
                <img src="WhatsApp Image 2024-08-27 at 08.55.37_e2654d09.jpg" alt="Golden Retriever">
                <p>Golden Retriever</p>
            </div>
            <div class="dog" onclick="openLightbox('img2')">
                <img src="WhatsApp Image 2024-08-27 at 08.54.47_e545c80d.jpg" alt="Beagle">
                <p>Beagle</p>
            </div>
            <div class="dog" onclick="openLightbox('img3')">
                <img src="WhatsApp Image 2024-08-27 at 08.55.16_ce32fdbb.jpg" alt="German Shepherd">
                <p>German Shepherd</p>
            </div>
            <div class="dog" onclick="openLightbox('img4')">
                <img src="lt.jpg" alt="Labrador Retriever">
                <p>Labrador Retriever</p>
            </div>
            <div class="dog" onclick="openLightbox('img5')">
                <img src="sh.jpg" alt="Siberian Husky">
                <p>Siberian Husky</p>
            </div>
            <div class="dog" onclick="openLightbox('img6')">
                <img src="ds.jpg" alt="Dachshund">
                <p>Dachshund</p>
            </div>
            <div class="dog" onclick="openLightbox('img7')">
                <img src="bc.jpg" alt="Border Collie">
                <p>Border Collie</p>
            </div>
            <div class="dog" onclick="openLightbox('img8')">
                <img src="aed.jpg" alt="American Eskimo Dog">
                <p>American Eskimo Dog</p>
            </div>
            <div class="dog" onclick="openLightbox('img9')">
                <img src="pwc.jpg" alt="Pembroke Welsh Corgi">
                <p>Pembroke Welsh Corgi</p>
            </div>
            <div class="dog" onclick="openLightbox('img10')">
                <img src="SI.jpg" alt="Shiba Inu">
                <p>Shiba Inu</p>
            </div>
            <div class="dog" onclick="openLightbox('img11')">
                <img src="sa.jpg" alt="Samoyed">
                <p>Samoyed</p>
            </div>
        </section>
    </main>

    <!-- Lightbox (popup) -->
    <div id="img1" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="WhatsApp Image 2024-08-27 at 08.55.37_e2654d09.jpg" alt="Golden Retriever">
    </div>
    <div id="img2" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="WhatsApp Image 2024-08-27 at 08.54.47_e545c80d.jpg" alt="Beagle">
    </div>
    <div id="img3" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="WhatsApp Image 2024-08-27 at 08.55.16_ce32fdbb.jpg" alt="German Shepherd">
    </div>
    <div id="img4" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="lt.jpg" alt="Labrador Retriever">
    </div>
    <div id="img5" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="sh.jpg" alt="Siberian Husky">
    </div>
    <div id="img6" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="ds.jpg" alt="Dachshund">
    </div>
    <div id="img7" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="bc.jpg" alt="Border Collie">
    </div>
    <div id="img8" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="aed.jpg" alt="American Eskimo Dog">
    </div>
    <div id="img9" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="pwc.jpg" alt="Pembroke Welsh Corgi">
    </div>
    <div id="img10" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="SI.jpg" alt="Shiba Inu">
    </div>
    <div id="img11" class="lightbox">
        <span class="close" onclick="closeLightbox()">X</span>
        <img src="sa.jpg" alt="Samoyed">
    </div>

    <footer>
        <p>&copy; 2024 Dog Lover's Paradise. All rights reserved.</p>
    </footer>

    <!-- Watermarks -->
    <div class="watermark watermark-1">DHARSHINI K-212223230047</div>
    <div class="watermark watermark-2">DHARSHINI K-212223230047</div>
    <div class="watermark watermark-3">DHARSHINI K-212223230047</div>


    <script>
        // JavaScript for opening and closing the lightbox
        function openLightbox(id) {
            document.getElementById(id).style.display = 'flex';
        }

        function closeLightbox() {
            let lightboxes = document.querySelectorAll('.lightbox');
            lightboxes.forEach(function(lightbox) {
                lightbox.style.display = 'none';
            });
        }
    </script>
</body>
</html>
~~~

## OUTPUT:

## RESULT:
The program to design, develop, and deploy an interactive image gallery web application with JavaScript functionality is completed successfully.
