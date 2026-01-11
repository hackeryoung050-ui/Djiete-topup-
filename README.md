<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mon Cœur pour Toi</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #fdf2f8;
            color: #5a3d5c;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, #d63384 0%, #8b5a9d 100%);
            color: white;
            text-align: center;
            padding: 40px 20px;
            border-radius: 0 0 30px 30px;
            box-shadow: 0 5px 15px rgba(139, 90, 157, 0.3);
            position: relative;
            overflow: hidden;
        }

        header:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, #ffd6e7, #ff9ec0, #ff6b9d, #ff4081);
        }

        .hearts-container {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
        }

        .heart {
            position: absolute;
            color: rgba(255, 255, 255, 0.7);
            font-size: 20px;
            animation: float 6s infinite linear;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }

        h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }

        .subtitle {
            font-size: 1.3rem;
            margin-bottom: 20px;
            opacity: 0.9;
        }

        /* Main Photo Animation */
        .main-photo-container {
            margin: 40px auto;
            max-width: 600px;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 30px rgba(214, 51, 132, 0.3);
            position: relative;
        }

        .main-photo {
            width: 100%;
            height: 400px;
            object-fit: cover;
            display: block;
            animation: heartbeat 2.5s infinite;
        }

        @keyframes heartbeat {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.03);
            }
        }

        .photo-overlay {
            position: absolute;
            bottom: 0;
            background: linear-gradient(to top, rgba(0, 0, 0, 0.7), transparent);
            color: white;
            width: 100%;
            padding: 20px;
            text-align: center;
        }

        /* Messages Section */
        .messages-section {
            background: white;
            border-radius: 20px;
            padding: 30px;
            margin: 40px 0;
            box-shadow: 0 10px 25px rgba(139, 90, 157, 0.1);
        }

        .section-title {
            color: #d63384;
            border-bottom: 2px solid #f8bbd9;
            padding-bottom: 10px;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section-title i {
            font-size: 1.5rem;
        }

        .message-box {
            background: #fdf2f8;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 30px;
            border-left: 5px solid #d63384;
        }

        .message-title {
            color: #8b5a9d;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .message-content {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .heart-emoji {
            color: #ff4081;
            font-size: 1.5rem;
            margin: 0 5px;
        }

        /* Photo Gallery */
        .gallery-section {
            background: white;
            border-radius: 20px;
            padding: 30px;
            margin: 40px 0;
            box-shadow: 0 10px 25px rgba(139, 90, 157, 0.1);
        }

        .gallery-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .photo-input-container {
            background: #f9f0ff;
            border: 2px dashed #d63384;
            border-radius: 15px;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 200px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .photo-input-container:hover {
            background: #f4e5ff;
            transform: translateY(-5px);
        }

        .photo-input-container i {
            font-size: 3rem;
            color: #d63384;
            margin-bottom: 15px;
        }

        .photo-input-container p {
            text-align: center;
            color: #8b5a9d;
        }

        .photo-item {
            position: relative;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            height: 200px;
        }

        .photo-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .photo-item:hover img {
            transform: scale(1.1);
        }

        /* Love Note */
        .love-note {
            background: linear-gradient(135deg, #ffd6e7 0%, #ffafcc 100%);
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            text-align: center;
            box-shadow: 0 10px 25px rgba(255, 107, 157, 0.2);
        }

        .love-note h2 {
            color: #d63384;
            margin-bottom: 20px;
        }

        .love-note p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 25px;
        }

        .signature {
            font-family: 'Dancing Script', cursive;
            font-size: 2.5rem;
            color: #8b5a9d;
            margin-top: 20px;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 30px;
            color: #8b5a9d;
            border-top: 1px solid #f8bbd9;
            margin-top: 40px;
        }

        .footer-heart {
            color: #ff4081;
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.2);
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.2rem;
            }
            
            .subtitle {
                font-size: 1.1rem;
            }
            
            .gallery-container {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            }
            
            .message-content {
                font-size: 1rem;
            }
            
            .main-photo {
                height: 300px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="hearts-container" id="heartsContainer"></div>
        <div class="container">
            <h1><i class="fas fa-heart"></i> Pour Mon Amour Éternel <i class="fas fa-heart"></i></h1>
            <p class="subtitle">Chaque moment avec toi est un trésor que je chéris</p>
        </div>
    </header>

    <div class="container">
        <div class="main-photo-container">
            <img src="https://files.catbox.moe/t7bg12.jpg" alt="Notre souvenir spécial" class="main-photo" id="mainPhoto">
            <div class="photo-overlay">
                <h2>Un moment inoubliable</h2>
                <p>Cette photo représente notre amour éternel</p>
            </div>
        </div>

        <div class="messages-section">
            <h2 class="section-title"><i class="fas fa-envelope-open-text"></i> Mes Messages pour Toi</h2>
            
            <div class="message-box">
                <h3 class="message-title"><i class="fas fa-memory"></i> Souvenir à la plage</h3>
                <div class="message-content">
                    <p>Tu te rappelles bébé ? C'était notre deuxième fois à la plage. On s'est évadé, on a fugué et nous y sommes allés. On s'est assis, embrassés et rigolé. T'as aimé le calme, le doux son de la plage. Il y avait un bateau, on s'est couchés dessus. On a fait des trucs, trucs 😅💕</p>
                    <p>On a failli se faire prendre, tu te rappelles ? Et puis l'heure a passé, nous avons continué nos activités jusqu'à oublier le temps passé. Je me rappelle comme si c'était hier. C'est dingue non 🤭❤️ On a traversé tellement de péripéties.</p>
                </div>
            </div>
            
            <div class="message-box">
                <h3 class="message-title"><i class="fas fa-birthday-cake"></i> Ton anniversaire inoubliable</h3>
                <div class="message-content">
                    <p>Et ça c'était le 15 juillet. Ton anniversaire, c'était magnifique. Je me suis donné à fond pour ce jour. J'ai voulu te faire plaisir 😅 Je crois que c'était plutôt réussi 💕 T'as aimé. Je t'ai décroché pas mal de sourires en ce jour 🤭❤️</p>
                    <p>Oui chérie, on a vécu pas mal de trucs en si peu de temps 🫂❤️ Chaque moment avec toi est spécial et restera gravé dans ma mémoire pour toujours.</p>
                </div>
            </div>
        </div>

        <div class="gallery-section">
            <h2 class="section-title"><i class="fas fa-images"></i> Notre Galerie de Souvenirs</h2>
            <p>Ajoute ici nos photos spéciales en entrant les URLs ci-dessous</p>
            
            <div class="gallery-container" id="galleryContainer">
                <!-- Les photos seront ajoutées ici dynamiquement -->
            </div>
            
            <div class="photo-input-container" onclick="document.getElementById('urlInputs').style.display='block'">
                <i class="fas fa-cloud-upload-alt"></i>
                <p>Clique ici pour ajouter jusqu'à 10 photos avec leurs URLs</p>
            </div>
            
            <div id="urlInputs" style="display: none; margin-top: 30px;">
                <h3 style="color: #d63384; margin-bottom: 15px;">Entrez les URLs de vos photos :</h3>
                <div id="inputContainer"></div>
                <button onclick="addPhotoInput()" style="background: #d63384; color: white; border: none; padding: 10px 20px; border-radius: 10px; cursor: pointer; margin-top: 15px;">
                    <i class="fas fa-plus"></i> Ajouter un champ URL
                </button>
                <button onclick="loadPhotos()" style="background: #8b5a9d; color: white; border: none; padding: 10px 20px; border-radius: 10px; cursor: pointer; margin-top: 15px; margin-left: 10px;">
                    <i class="fas fa-images"></i> Afficher les photos
                </button>
            </div>
        </div>

        <div class="love-note">
            <h2><i class="fas fa-heart"></i> Mon Engagement envers Toi <i class="fas fa-heart"></i></h2>
            <p>Ma chérie, à travers ces mots et ces souvenirs, je veux te rappeler à quel point tu es importante pour moi. Chaque jour à tes côtés est un cadeau, et même quand je fais des erreurs, mon amour pour toi ne faiblit jamais.</p>
            <p>Je m'excuse sincèrement pour les moments où j'ai pu te blesser, et je promets de toujours faire de mon mieux pour être l'homme que tu mérites. Notre histoire est le plus beau chapitre de ma vie, et j'ai hâte d'en écrire beaucoup d'autres avec toi.</p>
            <p>Je t'aime plus que les mots ne peuvent exprimer.</p>
            <div class="signature">Pour toujours ton homme</div>
        </div>
    </div>

    <footer>
        <p>Créé avec <span class="footer-heart"><i class="fas fa-heart"></i></span> pour la femme de ma vie</p>
        <p>Chaque jour avec toi est une bénédiction</p>
    </footer>

    <script>
        // Créer des cœurs flottants
        function createHearts() {
            const container = document.getElementById('heartsContainer');
            const heartCount = 25;
            
            for (let i = 0; i < heartCount; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.innerHTML = '❤';
                
                // Position aléatoire
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.animationDelay = Math.random() * 5 + 's';
                heart.style.fontSize = (Math.random() * 15 + 15) + 'px';
                
                container.appendChild(heart);
            }
        }

        // Initialiser la galerie
        function initializeGallery() {
            const galleryContainer = document.getElementById('galleryContainer');
            const inputContainer = document.getElementById('inputContainer');
            
            // Créer les placeholders pour les photos
            for (let i = 0; i < 10; i++) {
                const photoItem = document.createElement('div');
                photoItem.className = 'photo-item';
                photoItem.id = `photoItem${i}`;
                photoItem.innerHTML = `<img src="https://images.unsplash.com/photo-1518568814500-bf0f8d125f46?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="Placeholder photo ${i+1}">`;
                galleryContainer.appendChild(photoItem);
                
                // Ajouter un champ d'entrée pour l'URL
                const inputDiv = document.createElement('div');
                inputDiv.style.marginBottom = '10px';
                inputDiv.innerHTML = `
                    <label for="photoUrl${i}">Photo ${i+1}:</label>
                    <input type="text" id="photoUrl${i}" placeholder="https://example.com/photo${i+1}.jpg" style="width: 100%; padding: 8px; margin-top: 5px; border: 1px solid #d63384; border-radius: 5px;">
                `;
                inputContainer.appendChild(inputDiv);
            }
        }

        // Ajouter un champ URL supplémentaire
        function addPhotoInput() {
            const inputContainer = document.getElementById('inputContainer');
            const currentCount = inputContainer.children.length;
            
            if (currentCount < 15) {
                const inputDiv = document.createElement('div');
                inputDiv.style.marginBottom = '10px';
                inputDiv.innerHTML = `
                    <label for="photoUrl${currentCount}">Photo ${currentCount+1}:</label>
                    <input type="text" id="photoUrl${currentCount}" placeholder="https://example.com/photo${currentCount+1}.jpg" style="width: 100%; padding: 8px; margin-top: 5px; border: 1px solid #d63384; border-radius: 5px;">
                `;
                inputContainer.appendChild(inputDiv);
            } else {
                alert('Maximum 15 photos autorisées');
            }
        }

        // Charger les photos à partir des URLs
        function loadPhotos() {
            const inputContainer = document.getElementById('inputContainer');
            const inputs = inputContainer.getElementsByTagName('input');
            
            for (let i = 0; i < inputs.length; i++) {
                const url = inputs[i].value.trim();
                const photoItem = document.getElementById(`photoItem${i}`);
                
                if (url) {
                    // Si l'élément photo n'existe pas, le créer
                    if (!photoItem && i < 15) {
                        const galleryContainer = document.getElementById('galleryContainer');
                        const newPhotoItem = document.createElement('div');
                        newPhotoItem.className = 'photo-item';
                        newPhotoItem.id = `photoItem${i}`;
                        galleryContainer.appendChild(newPhotoItem);
                    }
                    
                    // Mettre à jour l'image
                    const imgElement = document.getElementById(`photoItem${i}`).querySelector('img');
                    if (imgElement) {
                        imgElement.src = url;
                        imgElement.onerror = function() {
                            this.src = 'https://images.unsplash.com/photo-1518568814500-bf0f8d125f46?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80';
                            alert(`L'URL de la photo ${i+1} n'a pas pu être chargée. L'image par défaut sera affichée.`);
                        };
                    }
                }
            }
            
            alert('Les photos ont été mises à jour!');
        }

        // Animation pour la photo principale
        function animateMainPhoto() {
            const photo = document.getElementById('mainPhoto');
            let scale = 1;
            let direction = 0.01;
            
            setInterval(() => {
                scale += direction;
                if (scale > 1.03 || scale < 1) {
                    direction *= -1;
                }
                photo.style.transform = `scale(${scale})`;
            }, 100);
        }

        // Initialisation
        window.onload = function() {
            createHearts();
            initializeGallery();
            
            // Démarrer l'animation de la photo principale
            setTimeout(() => {
                animateMainPhoto();
            }, 1000);
            
            // Ajouter un effet de frappe aux messages
            const messageContents = document.querySelectorAll('.message-content');
            messageContents.forEach(content => {
                const text = content.innerHTML;
                content.innerHTML = '';
                let i = 0;
                
                function typeWriter() {
                    if (i < text.length) {
                        content.innerHTML += text.charAt(i);
                        i++;
                        setTimeout(typeWriter, 10);
                    }
                }
                
                // Démarrer l'effet après un délai
                setTimeout(typeWriter, 500);
            });
        };
    </script>
</body>
</html>
