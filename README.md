# CadionActivity4
To be submitted to Sir Rustico
<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/gsap.min.js"></script>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: #222;
        }
        .particle {
            position: absolute;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: #FFF;
        }
    </style>
</head>
<body>
    <script>
        // Function to create a particle object
        function createParticle() {
            var particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * (window.innerWidth - 10) + 'px';
            particle.style.top = Math.random() * (window.innerHeight - 10) + 'px';
            document.body.appendChild(particle);
            return particle;
        }

        // Function to animate the particle
        function animateParticle(particle) {
            gsap.to(particle, {
                duration: Math.random() * 2 + 1,
                x: Math.random() * window.innerWidth,
                y: Math.random() * window.innerHeight,
                opacity: 0,
                scale: 0,
                onComplete: function() {
                    particle.parentNode.removeChild(particle);
                }
            });
        }

        // Create and animate particles
        function createAndAnimateParticles() {
            var particleCount = 50;
            for (var i = 0; i < particleCount; i++) {
                var particle = createParticle();
                animateParticle(particle);
            }
        }

        // Trigger particle creation and animation
        createAndAnimateParticles();
    </script>
</body>
</html>
