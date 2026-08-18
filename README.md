# Function showPage(pageId) {
            const pages = document.querySelectorAll('.page-section');
            pages.forEach(page => page.classList.remove('active'));

            const navLinks = document.querySelectorAll('nav a');
            navLinks.forEach(link => link.classList.remove('active'));

            document.getElementById(pageId).classList.add('active');

            const activeNav = document.getElementById('nav-' + pageId);
            if (activeNav) {
                activeNav.classList.add('active');
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function handleQuoteSubmit(e) {
            e.preventDefault();
            const name = document.getElementById('clientName').value;
            alert(`Thank you, ${name}! Your quote request has been sent to BLUE GRID WEB DESIGN. We will contact you shortly.`);
            document.getElementById('quoteForm').reset();
        }

        function generateVisualConcept() {
            const input = document.getElementById('aiInput').value.trim();
            const img = document.getElementById('aiPreviewImg');
            const placeholder = document.getElementById('placeholderMsg');

            if (!input) {
                alert('Please enter a description for your design concept.');
                return;
            }

            placeholder.style.display = 'none';
            img.style.display = 'block';
            
            // Unsplash Source fallback based on user search term
            const keyword = encodeURIComponent(input);
            img.src = `https://source.unsplash.com/featured/800x600/?website,${keyword}`;
        }
    </script>
</body>
</html>
