# ny
# gensis-
<html>
<head>
    <title>Exclusive NFT Gallery</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --primary-color: #A67C00;
            --primary-hover: #8B6914;
            --accent-gold: #FFD700;
            --background-dark: #0A0B0E;
            --card-bg: #141519;
            --text-light: #FFFFFF;
            --text-gold: #D4AF37;
            --premium-gradient: linear-gradient(135deg, #B8860B, #FFD700);
            --card-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
            --glass-effect: rgba(255, 255, 255, 0.05);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            min-height: 100vh;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: var(--background-dark);
            color: var(--text-light);
            background-image: 
                radial-gradient(circle at 20% 20%, rgba(255, 215, 0, 0.05) 0%, transparent 40%),
                radial-gradient(circle at 80% 80%, rgba(255, 215, 0, 0.05) 0%, transparent 40%);
        }

        .header {
            padding: 20px;
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(20px);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 215, 0, 0.1);
        }

        .header-content {
            max-width: 600px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8em;
            font-weight: 800;
            background: var(--premium-gradient);
            -webkit-background-clip: text;
            color: transparent;
            letter-spacing: 1px;
        }

        .connect-wallet {
            padding: 10px 20px;
            background: var(--premium-gradient);
            border: none;
            border-radius: 25px;
            color: var(--background-dark);
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .connect-wallet:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.2);
        }

        .gallery-container {
            max-width: 600px;
            margin: 100px auto 40px;
            padding: 20px;
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .artwork-card {
            background: var(--card-bg);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--card-shadow);
            transition: all 0.4s ease;
            border: 1px solid rgba(255, 215, 0, 0.1);
        }

        .artwork-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.1);
        }

        .artwork-image {
            position: relative;
            width: 100%;
            height: 400px;
            overflow: hidden;
        }

        .artwork-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .artwork-card:hover .artwork-image img {
            transform: scale(1.05);
        }

        .premium-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--premium-gradient);
            padding: 8px 16px;
            border-radius: 25px;
            font-size: 0.9em;
            font-weight: bold;
            color: var(--background-dark);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }

        .price-tag {
            position: absolute;
            bottom: 20px;
            left: 20px;
            background: rgba(0, 0, 0, 0.8);
            padding: 10px 20px;
            border-radius: 15px;
            color: var(--text-gold);
            font-weight: bold;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 215, 0, 0.2);
        }

        .artwork-info {
            padding: 25px;
            background: linear-gradient(to bottom, rgba(20, 21, 25, 0.8), rgba(10, 11, 14, 0.9));
        }

        .artwork-title {
            font-size: 1.4em;
            color: var(--text-gold);
            margin-bottom: 10px;
            font-weight: bold;
        }

        .artwork-collection {
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9em;
        }

        .action-buttons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .action-btn {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 12px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .buy-btn {
            background: var(--premium-gradient);
            color: var(--background-dark);
        }

        .view-btn {
            background: var(--glass-effect);
            color: var(--text-light);
            border: 1px solid rgba(255, 215, 0, 0.2);
        }

        .action-btn:hover {
            transform: translateY(-2px);
        }

        @media (max-width: 640px) {
            .gallery-container {
                padding: 15px;
                margin-top: 80px;
            }

            .artwork-image {
                height: 300px;
            }

            .artwork-title {
                font-size: 1.2em;
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <div class="header-content">
            <div class="logo">GENESIS NFT</div>
            <button class="connect-wallet">
                <i class="fas fa-wallet"></i>
                Connect
            </button>
        </div>
    </header>

    <div class="gallery-container">
        <!-- NFT Cards will be dynamically inserted here -->
    </div>

    <script>
        const nftData = [
            {
                id: 1,
                title: "Divine Harmony #001",
                collection: "Genesis Collection",
                price: "12.5 ETH",
                image: "https://i.ibb.co/yFNbRqF/Whats-App-Image-2024-10-20-at-09-16-07-510389dd.jpg",
                badge: "Genesis Edition"
            },
            {
                id: 2,
                title: "Ethereal Dreams #002",
                collection: "Platinum Series",
                price: "8.8 ETH",
                image: "https://i.ibb.co/7vkRDZv/Whats-App-Image-2024-10-20-at-09-16-08-0798f91f.jpg",
                badge: "Platinum"
            },
            {
                id: 3,
                title: "Quantum Legacy #003",
                collection: "Elite Collection",
                price: "15.2 ETH",
                image: "https://i.ibb.co/k8zNj9j/a-captivating-and-dreamlike-scene-of-a-dali-esque-swof-qz-GQu-Ks-Sj-h-EVGflw-q-Em-M-hmr-Rcm-FUZb-GUc.jpg",
                badge: "Ultra Rare"
            },
            {
                id: 4,
                title: "Celestial Vision #004",
                collection: "Masterpiece Series",
                price: "18.5 ETH",
                image: "https://i.ibb.co/k51wwwg/an-awe-inspiring-scene-of-mythical-beasts-roaming-E6-Ugt4-g-TAO4r-Pl-Gpra-e-Q-t0tr-Egk6-Sf2r8k-Tr2-I.jpg",
                badge: "Masterpiece"
            },
            {
                id: 5,
                title: "Digital Royalty #005",
                collection: "Crown Collection",
                price: "21.0 ETH",
                image: "https://i.ibb.co/YBXK5Mg/a-striking-3d-illustration-of-a-t-shirt-hanging-on-h1-AIHpnz-TRK-8e-SADc-LFJw-l-Hs-Od-YYj-Sp-Wg6xv-U.jpg",
                badge: "Royal Edition"
            }
        ];

        function createNFTCard(nft) {
            return `
                <div class="artwork-card">
                    <div class="artwork-image">
                        <div class="premium-badge">${nft.badge}</div>
                        <div class="price-tag">
                            <i class="fab fa-ethereum"></i> ${nft.price}
                        </div>
                        <img src="${nft.image}" alt="${nft.title}">
                    </div>
                    <div class="artwork-info">
                        <h3 class="artwork-title">${nft.title}</h3>
                        <p class="artwork-collection">${nft.collection}</p>
                        <div class="action-buttons">
                            <button class="action-btn buy-btn">Purchase Now</button>
                            <button class="action-btn view-btn">View Details</button>
                        </div>
                    </div>
                </div>
            `;
        }

        function renderGallery() {
            const gallery = document.querySelector('.gallery-container');
            gallery.innerHTML = nftData.map(nft => createNFTCard(nft)).join('');
        }

        window.onload = renderGallery;
    </script>
</body>
