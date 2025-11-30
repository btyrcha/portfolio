---
layout: default
title: My Photography Portfolio
---

# My analog photography portfolio

Hi! Welcome to my analog photography portfolio, 
where I present you some of my favourite shots.

Enjoy.

## Gallery

<div class="gallery">
  <a href="{{ site.baseurl }}/assets/photos/F1010008.jpg" class="gallery-item"><img src="{{ site.baseurl }}/assets/photos/F1010008.jpg" alt=""></a>
  <a href="{{ site.baseurl }}/assets/photos/F1050005.jpg" class="gallery-item"><img src="{{ site.baseurl }}/assets/photos/F1050005.jpg" alt=""></a>
  <a href="{{ site.baseurl }}/assets/photos/F1050022.jpg" class="gallery-item"><img src="{{ site.baseurl }}/assets/photos/F1050022.jpg" alt=""></a>
  <a href="{{ site.baseurl }}/assets/photos/F1050035.jpg" class="gallery-item"><img src="{{ site.baseurl }}/assets/photos/F1050035.jpg" alt=""></a>
  <a href="{{ site.baseurl }}/assets/photos/F1190009.jpg" class="gallery-item"><img src="{{ site.baseurl }}/assets/photos/F1190009.jpg" alt=""></a>
  <a href="{{ site.baseurl }}/assets/photos/F1190013.jpg" class="gallery-item"><img src="{{ site.baseurl }}/assets/photos/F1190013.jpg" alt=""></a>
</div>

<div id="lightbox" class="lightbox">
  <span class="close">&times;</span>
  <span class="prev">&#10094;</span>
  <span class="next">&#10095;</span>
  <img class="lightbox-content" id="lightbox-img">
  <div class="caption" id="caption"></div>
</div>

<script>
let currentIndex = 0;
const galleryItems = document.querySelectorAll('.gallery-item');
const lightbox = document.getElementById('lightbox');
const lightboxImg = document.getElementById('lightbox-img');
const caption = document.getElementById('caption');

galleryItems.forEach((item, index) => {
  item.addEventListener('click', (e) => {
    e.preventDefault();
    currentIndex = index;
    showLightbox();
  });
});

function showLightbox() {
  lightbox.style.display = 'flex';
  lightboxImg.src = galleryItems[currentIndex].href;
  caption.textContent = galleryItems[currentIndex].querySelector('img').alt;
}

document.querySelector('.close').onclick = () => {
  lightbox.style.display = 'none';
};

document.querySelector('.prev').onclick = () => {
  currentIndex = (currentIndex - 1 + galleryItems.length) % galleryItems.length;
  showLightbox();
};

document.querySelector('.next').onclick = () => {
  currentIndex = (currentIndex + 1) % galleryItems.length;
  showLightbox();
};

lightbox.onclick = (e) => {
  if (e.target === lightbox) {
    lightbox.style.display = 'none';
  }
};

document.addEventListener('keydown', (e) => {
  if (lightbox.style.display === 'flex') {
    if (e.key === 'ArrowLeft') {
      currentIndex = (currentIndex - 1 + galleryItems.length) % galleryItems.length;
      showLightbox();
    } else if (e.key === 'ArrowRight') {
      currentIndex = (currentIndex + 1) % galleryItems.length;
      showLightbox();
    } else if (e.key === 'Escape') {
      lightbox.style.display = 'none';
    }
  }
});
</script>

© 2025 Bartosz Tyrcha
