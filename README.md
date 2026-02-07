# Saki-sushi
Pagina de muestra a restaurante saki sushi ccs


<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🍣 Saki Sushi</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800&family=Roboto:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #D32F2F;
            --secondary: #212121;
            --accent: #FF9800;
            --light: #F5F5F5;
            --dark: #121212;
            --warm: #FFC107;
            --success: #388E3C;
            --shadow: rgba(0, 0, 0, 0.15);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Roboto', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8)), 
                        url('https://images.unsplash.com/photo-1565299624946-b28f40a0ca4b?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-attachment: fixed;
            background-position: center;
            min-height: 100vh;
            padding: 20px;
            color: var(--secondary);
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            background: var(--light);
            border-radius: 15px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.25);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, var(--primary), #B71C1C);
            color: white;
            padding: 25px 30px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            opacity: 0.2;
        }

        .logo-container {
            margin-bottom: 10px;
        }

        .logo {
            max-width: 180px;
            height: auto;
            filter: drop-shadow(2px 4px 6px rgba(0,0,0,0.4));
            border-radius: 10px;
        }

        h1 {
            font-size: 3.2em;
            margin-bottom: 5px;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.4);
            font-family: 'Montserrat', sans-serif;
            font-weight: 800;
            position: relative;
            z-index: 1;
            color: white;
            letter-spacing: 1px;
        }

        .subtitle {
            font-size: 1.4em;
            opacity: 0.95;
            margin-bottom: 15px;
            position: relative;
            z-index: 1;
            color: var(--warm);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-family: 'Montserrat', sans-serif;
        }

        .categories-nav {
            background: var(--secondary);
            padding: 15px 30px;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 5px 20px rgba(0,0,0,0.3);
        }

        .categories-container {
            display: flex;
            overflow-x: auto;
            gap: 10px;
            padding-bottom: 5px;
            scrollbar-width: thin;
            scrollbar-color: var(--accent) rgba(255,255,255,0.1);
        }

        .categories-container::-webkit-scrollbar {
            height: 6px;
        }

        .categories-container::-webkit-scrollbar-track {
            background: rgba(255,255,255,0.1);
            border-radius: 3px;
        }

        .categories-container::-webkit-scrollbar-thumb {
            background: var(--accent);
            border-radius: 3px;
        }

        .category-tab {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            padding: 10px 20px;
            border-radius: 50px;
            font-size: 0.9em;
            white-space: nowrap;
            cursor: pointer;
            transition: var(--transition);
            border: 2px solid transparent;
            flex-shrink: 0;
            font-family: 'Montserrat', sans-serif;
            font-weight: 500;
        }

        .category-tab:hover {
            background: rgba(255, 255, 255, 0.2);
            border-color: var(--accent);
            transform: translateY(-2px);
        }

        .category-tab.active {
            background: var(--accent);
            color: var(--secondary);
            font-weight: 700;
            box-shadow: 0 3px 10px rgba(255, 152, 0, 0.4);
        }

        .subcategories {
            display: none;
            background: rgba(33, 33, 33, 0.95);
            padding: 10px 30px;
            flex-wrap: wrap;
            gap: 10px;
        }

        .subcategory-tab {
            background: rgba(255, 255, 255, 0.15);
            color: white;
            padding: 8px 15px;
            border-radius: 30px;
            font-size: 0.85em;
            cursor: pointer;
            transition: var(--transition);
            font-family: 'Roboto', sans-serif;
        }

        .subcategory-tab:hover {
            background: rgba(255, 255, 255, 0.25);
        }

        .tagline {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 15px;
            position: relative;
            z-index: 1;
        }

        .tagline-item {
            background: rgba(255, 255, 255, 0.25);
            padding: 8px 15px;
            border-radius: 50px;
            font-size: 0.85em;
            backdrop-filter: blur(5px);
            font-family: 'Montserrat', sans-serif;
            font-weight: 500;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
            padding: 40px 30px;
        }

        @media (max-width: 992px) {
            .menu-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 768px) {
            .menu-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 20px;
            }
        }

        @media (max-width: 576px) {
            .menu-grid {
                grid-template-columns: 1fr;
            }
        }

        .menu-item {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 40px var(--shadow);
            transition: var(--transition);
            border: 2px solid transparent;
        }

        .menu-item:hover {
            transform: translateY(-10px);
            border-color: var(--accent);
            box-shadow: 0 20px 50px rgba(255, 152, 0, 0.2);
        }

        .item-image {
            height: 250px;
            width: 100%;
            background-size: cover;
            background-position: center;
            position: relative;
        }

        .item-image::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 60px;
            background: linear-gradient(transparent, rgba(0,0,0,0.5));
        }

        /* Imágenes únicas para cada platillo */
        .image-sashimi { background-image: url('https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); }
        .image-coquitos { background-image: url('https://images.unsplash.com/photo-1553621042-f6e147245754?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); }
        .image-langostinos { background-image: url('https://images.unsplash.com/photo-1621996346565-e3dbc353d2af?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); }
        .image-sushi-pizza { background-image: url('https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); }
        .image-ceviche { background-image: url('https://images.unsplash.com/photo-1551503759-5c9c09a53f8e?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); }
        .image-ceviche-mixto { background-image: url('https://images.unsplash.com/photo-1551503759-5c9c09a53f8e?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); }
        .image-tiradito { background-image: url('https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); }
        .image-maguro { background-image: url('https://images.unsplash.com/photo-1611143669185-af224c5e3252?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); }
        .image-sushi-deluxe { background-image: url('https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); }
        .image-margarita { background-image: url('https://images.unsplash.com/photo-1514362545857-3bc16c4c7d1b?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); }

        .item-header {
            padding: 25px;
            background: linear-gradient(to right, var(--secondary), #424242);
            color: white;
        }

        .item-name {
            font-size: 1.8em;
            font-weight: 700;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-family: 'Montserrat', sans-serif;
        }

        .item-price {
            font-size: 1.8em;
            color: var(--warm);
            font-weight: 700;
        }

        .item-description {
            color: #E0E0E0;
            font-size: 0.95em;
            line-height: 1.5;
            opacity: 0.9;
            font-family: 'Roboto', sans-serif;
        }

        .item-content {
            padding: 25px;
        }

        .quantity-section {
            background: #F8F8F8;
            padding: 20px;
            border-radius: 12px;
            margin-bottom: 20px;
            border: 2px solid #E0E0E0;
        }

        .quantity-controls {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            margin-bottom: 15px;
        }

        .qty-btn {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            border: none;
            background: linear-gradient(135deg, var(--primary), #B71C1C);
            color: white;
            font-size: 1.8em;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            box-shadow: 0 5px 15px rgba(211, 47, 47, 0.3);
        }

        .qty-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 20px rgba(211, 47, 47, 0.4);
        }

        .qty-btn:disabled {
            background: #BDBDBD;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .item-quantity {
            font-size: 2.5em;
            font-weight: 700;
            color: var(--secondary);
            min-width: 70px;
            text-align: center;
            font-family: 'Montserrat', sans-serif;
        }

        .item-stock {
            text-align: center;
            font-size: 0.95em;
            padding: 12px;
            border-radius: 10px;
            background: white;
            border: 2px solid;
            font-weight: 600;
            font-family: 'Roboto', sans-serif;
        }

        .available { border-color: var(--success); color: var(--success); }
        .low { border-color: var(--accent); color: var(--accent); }
        .sold-out { border-color: var(--primary); color: var(--primary); }

        .ingredients-section {
            background: #F8F8F8;
            border-radius: 12px;
            padding: 25px;
            margin-top: 15px;
            border: 2px solid #E0E0E0;
            max-height: 800px;
            overflow: hidden;
            transition: max-height 0.5s ease, opacity 0.3s ease, padding 0.3s ease, margin 0.3s ease;
        }

        .ingredients-section.hidden {
            max-height: 0;
            opacity: 0;
            padding: 0;
            margin-top: 0;
            border-width: 0;
        }

        .ingredients-title {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 3px solid var(--accent);
        }

        .ingredients-title i {
            color: var(--primary);
            font-size: 1.5em;
        }

        .ingredients-title h3 {
            font-family: 'Montserrat', sans-serif;
            font-weight: 600;
            color: var(--secondary);
        }

        .ingredient-options {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 12px;
            max-height: 300px;
            overflow-y: auto;
            padding-right: 10px;
        }

        .ingredient-options::-webkit-scrollbar {
            width: 8px;
        }

        .ingredient-options::-webkit-scrollbar-track {
            background: #F0F0F0;
            border-radius: 4px;
        }

        .ingredient-options::-webkit-scrollbar-thumb {
            background: var(--primary);
            border-radius: 4px;
        }

        .ingredient-option {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 15px;
            border-radius: 10px;
            cursor: pointer;
            transition: var(--transition);
            background: white;
            border: 2px solid #E0E0E0;
        }

        .ingredient-option:hover {
            border-color: var(--primary);
            transform: translateX(5px);
        }

        .ingredient-option.complete-option {
            background: linear-gradient(135deg, #E8F5E9, #C8E6C9);
            border: 2px solid var(--success);
        }

        .ingredient-option.complete-option:hover {
            background: linear-gradient(135deg, #C8E6C9, #A5D6A7);
        }

        .ingredient-option.complete-option.selected {
            background: linear-gradient(135deg, var(--success), #2E7D32);
            color: white;
        }

        .ingredient-checkbox {
            width: 22px;
            height: 22px;
            border: 2px solid var(--primary);
            border-radius: 5px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
            transition: var(--transition);
            cursor: pointer;
            position: relative;
        }

        .ingredient-checkbox.checked {
            background: var(--primary);
            border-color: var(--primary);
        }

        .ingredient-checkbox.checked::after {
            content: '✓';
            color: white;
            font-size: 14px;
            font-weight: bold;
            position: absolute;
        }

        .ingredient-icon {
            font-size: 1.3em;
            width: 30px;
            text-align: center;
        }

        .ingredient-name {
            font-weight: 500;
            color: var(--secondary);
            font-family: 'Roboto', sans-serif;
        }

        .joke-notice {
            background: linear-gradient(135deg, #FFF3E0, #FFE0B2);
            border: 2px solid var(--warm);
            border-radius: 10px;
            padding: 15px;
            margin-top: 15px;
            text-align: center;
            display: none;
            animation: fadeIn 0.5s ease;
            font-family: 'Roboto', sans-serif;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .ingredient-actions {
            display: flex;
            gap: 15px;
            margin-top: 25px;
            padding-top: 20px;
            border-top: 2px solid #E0E0E0;
        }

        .confirm-btn {
            flex: 1;
            padding: 18px;
            border: none;
            border-radius: 10px;
            font-size: 1.1em;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            transition: var(--transition);
            background: linear-gradient(135deg, var(--primary), #B71C1C);
            color: white;
            box-shadow: 0 5px 15px rgba(211, 47, 47, 0.3);
            font-family: 'Montserrat', sans-serif;
        }

        .confirm-btn:hover:not(:disabled) {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(211, 47, 47, 0.4);
        }

        .confirm-btn:disabled {
            background: #BDBDBD;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .price-adjustment {
            margin-top: 20px;
            padding: 20px;
            background: linear-gradient(135deg, #FFF8E1, #FFECB3);
            border-radius: 10px;
            text-align: center;
            border: 2px solid var(--warm);
            display: none;
            animation: pulse 2s infinite;
            font-family: 'Roboto', sans-serif;
        }

        @keyframes pulse {
            0%, 100% { box-shadow: 0 0 0 0 rgba(255, 193, 7, 0.3); }
            50% { box-shadow: 0 0 0 10px rgba(255, 193, 7, 0); }
        }

        .max-reached-notice {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            text-align: center;
            z-index: 1002;
            display: none;
            animation: popIn 0.5s ease;
            border: 4px solid var(--primary);
            max-width: 500px;
            width: 90%;
        }

        @keyframes popIn {
            0% { transform: translate(-50%, -50%) scale(0.5); opacity: 0; }
            100% { transform: translate(-50%, -50%) scale(1); opacity: 1; }
        }

        .max-reached-notice i {
            font-size: 4em;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .order-summary-section {
            background: #F8F8F8;
            padding: 40px 30px;
            margin: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 40px var(--shadow);
            border: 3px solid var(--primary);
        }

        .summary-title {
            font-size: 2.2em;
            color: var(--secondary);
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            gap: 15px;
            font-family: 'Montserrat', sans-serif;
            font-weight: 700;
            padding-bottom: 20px;
            border-bottom: 4px solid var(--accent);
        }

        .order-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
            margin-bottom: 30px;
        }

        @media (max-width: 768px) {
            .order-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 576px) {
            .order-grid {
                grid-template-columns: 1fr;
            }
        }

        .order-item-card {
            background: white;
            border-radius: 12px;
            padding: 25px;
            position: relative;
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
            border-left: 5px solid var(--primary);
            transition: var(--transition);
        }

        .order-item-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 30px rgba(0,0,0,0.15);
        }

        .instance-number {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--primary);
            color: white;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            box-shadow: 0 3px 10px rgba(211, 47, 47, 0.3);
        }

        .item-instance {
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 2px dashed #E0E0E0;
        }

        .item-instance:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }

        .order-item-info {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
        }

        .order-item-name {
            font-size: 1.4em;
            color: var(--secondary);
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
            font-family: 'Montserrat', sans-serif;
        }

        .order-item-modifiers {
            font-size: 0.95em;
            color: #616161;
            margin-top: 8px;
            padding: 10px;
            background: #F5F5F5;
            border-radius: 8px;
            border-left: 3px solid var(--accent);
            font-family: 'Roboto', sans-serif;
        }

        .order-item-price {
            font-size: 1.5em;
            font-weight: 700;
            color: var(--primary);
            min-width: 80px;
            text-align: right;
            font-family: 'Montserrat', sans-serif;
        }

        .summary-total-items {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 30px;
            padding-top: 25px;
            border-top: 4px solid var(--accent);
            font-size: 1.3em;
            font-weight: 600;
            font-family: 'Montserrat', sans-serif;
        }

        .items-total {
            color: var(--primary);
            font-size: 1.8em;
            font-weight: 700;
        }

        .order-section {
            padding: 40px;
            text-align: center;
            background: linear-gradient(135deg, var(--secondary), #424242);
            margin: 30px;
            border-radius: 15px;
        }

        .order-btn {
            background: linear-gradient(135deg, var(--primary), #B71C1C);
            color: white;
            border: none;
            padding: 25px 80px;
            font-size: 1.6em;
            font-weight: 700;
            border-radius: 50px;
            cursor: pointer;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 20px;
            box-shadow: 0 10px 30px rgba(211, 47, 47, 0.4);
            font-family: 'Montserrat', sans-serif;
        }

        .order-btn:hover:not(:disabled) {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 40px rgba(211, 47, 47, 0.5);
        }

        .order-btn:disabled {
            background: #BDBDBD;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .footer {
            background: var(--secondary);
            color: white;
            padding: 40px;
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 30px;
        }

        .footer-left {
            width: 100%;
            max-width: 500px;
            text-align: center;
        }

        .footer-logo {
            max-width: 150px;
            height: auto;
            margin-bottom: 20px;
            filter: drop-shadow(2px 4px 6px rgba(0,0,0,0.4));
            border-radius: 10px;
        }

        .footer-right {
            width: 100%;
            max-width: 500px;
            text-align: center;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            gap: 20px;
            margin-top: 10px;
        }

        .footer-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 5px;
            font-size: 1.1em;
            margin-bottom: 20px;
            font-family: 'Roboto', sans-serif;
        }

        .footer-item strong {
            font-family: 'Montserrat', sans-serif;
            font-weight: 600;
            color: var(--warm);
        }

        .footer-item a {
            color: white;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-item a:hover {
            color: var(--accent);
            text-decoration: underline;
        }

        .social-media {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }

        .social-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2em;
            color: white;
            transition: var(--transition);
            text-decoration: none;
        }

        .social-icon:hover {
            background: var(--accent);
            transform: translateY(-3px);
            color: var(--secondary);
        }

        .whatsapp-link {
            color: #25D366;
            font-weight: 600;
            font-size: 1.1em;
            font-family: 'Montserrat', sans-serif;
        }

        .whatsapp-link:hover {
            color: #1da851;
        }

        .footer-contact-info {
            background: rgba(255, 255, 255, 0.1);
            padding: 25px;
            border-radius: 12px;
            margin-top: 20px;
            width: 100%;
            max-width: 500px;
        }

        .contact-column {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.7);
            display: none;
            z-index: 1000;
            backdrop-filter: blur(5px);
        }

        .notification, .inventory-alert, .inventory-error {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            border-radius: 15px;
            box-shadow: 0 25px 60px rgba(0,0,0,0.3);
            z-index: 1001;
            display: none;
            animation: fadeInUp 0.4s ease;
            overflow: hidden;
            max-width: 600px;
            width: 90%;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translate(-50%, -40%); }
            to { opacity: 1; transform: translate(-50%, -50%); }
        }

        .thank-you {
            background: linear-gradient(135deg, var(--primary), #B71C1C);
            color: white;
            padding: 25px;
            border-radius: 12px;
            margin-top: 30px;
            text-align: center;
            font-size: 1.3em;
            font-weight: 600;
            display: none;
            animation: fadeIn 0.5s ease;
            font-family: 'Montserrat', sans-serif;
        }

        @media (max-width: 768px) {
            h1 { font-size: 2.5em; }
            .menu-grid { padding: 20px; }
            .item-name { font-size: 1.5em; }
            .order-section { padding: 30px 20px; }
            .order-btn { padding: 20px 40px; font-size: 1.3em; }
            .ingredient-options { grid-template-columns: 1fr; }
            .footer { padding: 30px 20px; }
        }

        @media (max-width: 480px) {
            .header { padding: 20px 15px; }
            .tagline { flex-direction: column; gap: 10px; }
            .quantity-controls { gap: 15px; }
            .qty-btn { width: 45px; height: 45px; }
            .categories-container { gap: 8px; }
            .category-tab { padding: 8px 15px; font-size: 0.8em; }
            .footer-contact-info { padding: 20px 15px; }
        }
    </style>
</head>
<body>
    <div class="overlay" id="overlay"></div>

    <div class="max-reached-notice" id="maxReachedNotice">
        <i class="fas fa-trophy"></i>
        <h2 style="color: var(--primary); margin-bottom: 15px; font-family: 'Montserrat', sans-serif;">¡Llevas todo el stock!</h2>
        <p style="font-size: 1.2em; margin-bottom: 10px; font-family: 'Roboto', sans-serif;">Has agregado <span id="maxQuantity" style="font-weight: bold; color: var(--primary);">0</span> unidades de este platillo.</p>
        <p style="color: var(--secondary); margin-bottom: 25px; font-family: 'Roboto', sans-serif;">¡No queda más disponible en la tienda!</p>
        <button onclick="closeMaxNotice()" style="background: var(--primary); color: white; border: none; padding: 15px 40px; border-radius: 10px; font-size: 1.1em; font-weight: bold; cursor: pointer; font-family: 'Montserrat', sans-serif;">
            ¡Entendido!
        </button>
    </div>

    <!-- Nuevo modal para error de inventario con cantidad máxima -->
    <div class="inventory-error" id="inventoryError">
        <div style="background: linear-gradient(135deg, #D32F2F, #B71C1C); padding: 30px; color: white;">
            <h2 style="font-size: 1.8em; display: flex; align-items: center; gap: 15px; font-family: 'Montserrat', sans-serif;">
                <i class="fas fa-exclamation-circle"></i>
                ¡Inventario Insuficiente!
            </h2>
        </div>
        <div style="padding: 30px;">
            <div id="inventoryErrorContent" style="max-height: 300px; overflow-y: auto; padding: 20px; background: #F5F5F5; border-radius: 10px; margin-bottom: 20px;">
                <!-- Los detalles del error aparecerán aquí -->
            </div>
            <p id="maxPossibleOrder" style="text-align: center; margin-top: 15px; color: #666; font-family: 'Roboto', sans-serif; font-style: italic;">
                <!-- Cantidad máxima posible aparecerá aquí -->
            </p>
            <button onclick="closeInventoryError()" style="background: var(--primary); color: white; border: none; padding: 15px 40px; border-radius: 10px; font-size: 1.1em; font-weight: bold; cursor: pointer; width: 100%; margin-top: 10px; font-family: 'Montserrat', sans-serif;">
                Entendido
            </button>
        </div>
    </div>

    <div class="container">
        <div class="header">
            <div class="logo-container">
                <img src="https://lh3.googleusercontent.com/pw/AP1GczPrZAoWxmsOGRD9xl1hO5Q65JXuwUZzoR6gUk-cw5lVmarxQe_-lwqpA60tTKLlXfpvIjAJlKC6jFls-xETJOPkebLIIPhbGlUkknmhrRbdhMUll2UViGSUj3WmHKg2YEsZlAfxBPPTjIHhScjD0jfe=w1439-h1439-s-no-gm" alt="Saki Sushi Logo" class="logo">
            </div>
            <h1>Saki Sushi</h1>
            <p class="subtitle">Adictos al universo saki</p>
            <div class="tagline">
                <div class="tagline-item">🐟 Fresco del día</div>
                <div class="tagline-item">🎌 Tradicional</div>
                <div class="tagline-item">👨‍🍳 Chef experto</div>
            </div>
        </div>

        <div class="categories-nav">
            <div class="categories-container" id="categoriesContainer">
                <div class="category-tab active" onclick="filterCategory('todos')">🍽️ Todos</div>
                <div class="category-tab" onclick="filterCategory('entradas')">🥢 Entradas</div>
                <div class="category-tab" onclick="filterCategory('sushi')">🍣 Sushi</div>
                <div class="category-tab" onclick="showSubcategories('rolls')">🍱 Rolls</div>
                <div class="category-tab" onclick="filterCategory('tragos')">🍹 Tragos</div>
                <div class="category-tab" onclick="filterCategory('pokes')">🥗 Pokes</div>
                <div class="category-tab" onclick="filterCategory('ensaladas')">🥬 Ensaladas</div>
                <div class="category-tab" onclick="showSubcategories('china')">🥡 Comida China</div>
                <div class="category-tab" onclick="showSubcategories('japonesa')">🎌 Comida Japonesa</div>
                <div class="category-tab" onclick="filterCategory('ninos')">👶 Para Niños</div>
                <div class="category-tab" onclick="filterCategory('ejecutivo')">💼 Combo Ejecutivo</div>
            </div>
            
            <div class="subcategories" id="subcategories-rolls">
                <div class="subcategory-tab" onclick="filterSubcategory('rolls-frios')">Rolls Fríos (10 pzas)</div>
                <div class="subcategory-tab" onclick="filterSubcategory('rolls-tempura')">Rolls Tempura (12 pzas)</div>
            </div>
            
            <div class="subcategories" id="subcategories-china">
                <div class="subcategory-tab" onclick="filterSubcategory('arroz-chino')">Arroz Chino</div>
                <div class="subcategory-tab" onclick="filterSubcategory('arroz-cantones')">Arroz Cantones</div>
                <div class="subcategory-tab" onclick="filterSubcategory('chopsuey')">Chopsuey</div>
                <div class="subcategory-tab" onclick="filterSubcategory('lomey')">Lomey</div>
                <div class="subcategory-tab" onclick="filterSubcategory('chow-mein')">Chow Mein</div>
                <div class="subcategory-tab" onclick="filterSubcategory('fideos-arroz')">Fideos de Arroz</div>
                <div class="subcategory-tab" onclick="filterSubcategory('tallarines-cantones')">Tallarines Cantones</div>
                <div class="subcategory-tab" onclick="filterSubcategory('mariscos')">Mariscos</div>
                <div class="subcategory-tab" onclick="filterSubcategory('foo-yung')">Foo Yong</div>
                <div class="subcategory-tab" onclick="filterSubcategory('sopas')">Sopas</div>
                <div class="subcategory-tab" onclick="filterSubcategory('entremeses')">Entremeses</div>
            </div>
            
            <div class="subcategories" id="subcategories-japonesa">
                <div class="subcategory-tab" onclick="filterSubcategory('yakimeshi')">Yakimeshi</div>
                <div class="subcategory-tab" onclick="filterSubcategory('yakisoba')">Yakisoba</div>
                <div class="subcategory-tab" onclick="filterSubcategory('pasta-udon')">Pasta Udon</div>
                <div class="subcategory-tab" onclick="filterSubcategory('churrasco')">Churrasco</div>
            </div>
        </div>

        <div class="menu-grid" id="menuGrid">
        </div>

        <div class="order-summary-section">
            <div class="summary-title">
                <i class="fas fa-shopping-cart"></i>
                Tu Pedido de Sushi
            </div>
            
            <div id="orderSummaryContent">
                <div class="empty-summary" style="text-align: center; padding: 40px; color: #888; font-style: italic;">
                    <i class="fas fa-sushi-roll" style="font-size: 3em; margin-bottom: 20px; color: var(--primary);"></i>
                    <p style="font-size: 1.2em;">Aún no has seleccionado ningún platillo</p>
                    <p style="margin-top: 10px;">Usa los botones + para comenzar tu pedido</p>
                </div>
            </div>
        </div>

        <div class="order-section">
            <button class="order-btn" id="orderBtn" onclick="placeOrder()" disabled>
                <i class="fas fa-check-circle"></i>
                CONFIRMAR PEDIDO
            </button>
            <div class="thank-you" id="thankYouMessage">
                <i class="fas fa-heart"></i>
                ¡Arigatō gozaimasu! Tu pedido está siendo preparado
            </div>
        </div>

        <div class="footer">
            <div class="footer-left">
                <img src="https://lh3.googleusercontent.com/pw/AP1GczPrZAoWxmsOGRD9xl1hO5Q65JXuwUZzoR6gUk-cw5lVmarxQe_-lwqpA60tTKLlXfpvIjAJlKC6jFls-xETJOPkebLIIPhbGlUkknmhrRbdhMUll2UViGSUj3WmHKg2YEsZlAfxBPPTjIHhScjD0jfe=w1439-h1439-s-no-gm" alt="Saki Sushi Logo" class="footer-logo">
                <p class="subtitle" style="font-size: 1.1em; text-align: center; margin-bottom: 20px; color: var(--warm);">Adictos al universo saki</p>
                <div class="social-media">
                    <a href="https://www.tiktok.com/@sakisushiccs?_r=1&_t=ZS-93hZW3nUNUo" class="social-icon" target="_blank">
                        <i class="fab fa-tiktok"></i>
                    </a>
                    <a href="https://www.instagram.com/sakisushiccs?igsh=cXZwOGdlMDVpYXR1" class="social-icon" target="_blank">
                        <i class="fab fa-instagram"></i>
                    </a>
                </div>
            </div>
            
            <div class="footer-right">
                <div class="footer-contact-info">
                    <div class="contact-column">
                        <div class="footer-item">
                            <i class="fas fa-clock"></i>
                            <span><strong>Abierto:</strong> 11:30am a 10:00pm</span>
                        </div>
                        
                        <div class="footer-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <div>
                                <strong>Av Universidad, Caracas</strong><br>
                                <a href="https://wa.me/5804242884773" class="whatsapp-link" target="_blank">+580424-2884773</a><br>
                                <a href="https://wa.me/5804242884772" class="whatsapp-link" target="_blank">+580424-2884772</a>
                            </div>
                        </div>
                        
                        <div class="footer-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <div>
                                <strong>San Bernardino, Caracas</strong><br>
                                <a href="https://wa.me/5804241722322" class="whatsapp-link" target="_blank">+580424-1722322</a><br>
                                <a href="https://wa.me/5804241722339" class="whatsapp-link" target="_blank">+580424-1722339</a>
                            </div>
                        </div>
                    </div>
                </div>
                
                <p style="opacity: 0.8; font-size: 0.9em; margin-top: 20px; font-family: 'Roboto', sans-serif;">
                    🎌 魚は新鮮です • 🍶 最高の食材
                </p>
            </div>
        </div>
    </div>

    <div class="notification" id="notification">
        <div style="background: linear-gradient(135deg, var(--primary), #B71C1C); padding: 30px; color: white;">
            <h2 style="font-size: 1.8em; display: flex; align-items: center; gap: 15px; font-family: 'Montserrat', sans-serif;">
                <i class="fas fa-check-circle"></i>
                ¡Pedido Confirmado!
            </h2>
        </div>
        <div style="padding: 30px;">
            <div id="orderDetails" style="max-height: 400px; overflow-y: auto; padding: 20px; background: #F5F5F5; border-radius: 10px;">
            </div>
            <div style="display: flex; justify-content: space-between; align-items: center; margin-top: 30px; padding-top: 20px; border-top: 2px solid #E0E0E0;">
                <span style="font-size: 1.4em; font-weight: bold; color: var(--secondary); font-family: 'Montserrat', sans-serif;">Total:</span>
                <span id="orderTotalPrice" style="font-size: 2em; font-weight: bold; color: var(--primary); font-family: 'Montserrat', sans-serif;">Bs. 0,00</span>
            </div>
            <p style="text-align: center; margin-top: 25px; color: #666; font-family: 'Roboto', sans-serif;">
                <i class="fas fa-clock"></i> Tu sushi estará listo en 15-20 minutos
            </p>
            <button onclick="closeNotification()" style="background: var(--primary); color: white; border: none; padding: 15px 40px; border-radius: 10px; font-size: 1.1em; font-weight: bold; cursor: pointer; width: 100%; margin-top: 20px; font-family: 'Montserrat', sans-serif;">
                Cerrar
            </button>
        </div>
    </div>

    <div class="inventory-alert" id="inventoryAlert">
        <div style="background: linear-gradient(135deg, #FF9800, #F57C00); padding: 25px; color: white;">
            <h2 style="font-size: 1.6em; display: flex; align-items: center; gap: 12px; font-family: 'Montserrat', sans-serif;">
                <i class="fas fa-exclamation-triangle"></i>
                Inventario Bajo
            </h2>
        </div>
        <div style="padding: 25px;">
            <div id="alertContent">
            </div>
            <button onclick="closeInventoryAlert()" style="background: #FF9800; color: white; border: none; padding: 15px 40px; border-radius: 10px; font-size: 1.1em; font-weight: bold; cursor: pointer; width: 100%; margin-top: 20px; font-family: 'Montserrat', sans-serif;">
                Entendido
            </button>
        </div>
    </div>

    <script>
        const TASA_CAMBIO = 400;
        
        const inventory = {
            arroz_sushi: { name: "Arroz para sushi", quantity: 5000, icon: "🍚", unit: "g", priceReduction: 1.50 * TASA_CAMBIO, required: true },
            alga_nori: { name: "Alga nori", quantity: 50, icon: "🌿", priceReduction: 0.80 * TASA_CAMBIO, required: true },
            wasabi: { name: "Wasabi", quantity: 200, icon: "💚", unit: "g", priceReduction: 0.60 * TASA_CAMBIO },
            jengibre: { name: "Jengibre encurtido", quantity: 300, icon: "🫚", unit: "g", priceReduction: 0.40 * TASA_CAMBIO },
            salmon: { name: "Salmón fresco", quantity: 30, icon: "🐟", priceReduction: 3.50 * TASA_CAMBIO, required: true },
            atun: { name: "Atún rojo", quantity: 25, icon: "🔴", priceReduction: 4.00 * TASA_CAMBIO, required: true },
            pescado_blanco: { name: "Pescado blanco", quantity: 20, icon: "🐠", priceReduction: 3.00 * TASA_CAMBIO, required: true },
            camaron: { name: "Camarón tigre", quantity: 40, icon: "🦐", priceReduction: 2.80 * TASA_CAMBIO },
            pulpo: { name: "Pulpo", quantity: 20, icon: "🐙", priceReduction: 3.20 * TASA_CAMBIO },
            aguacate: { name: "Aguacate", quantity: 25, icon: "🥑", priceReduction: 1.20 * TASA_CAMBIO },
            pepino: { name: "Pepino japonés", quantity: 20, icon: "🥒", priceReduction: 0.70 * TASA_CAMBIO },
            cangrejo: { name: "Carne de cangrejo", quantity: 30, icon: "🦀", priceReduction: 2.50 * TASA_CAMBIO },
            salsa_soja: { name: "Salsa de soja", quantity: 1000, icon: "🥢", unit: "ml", priceReduction: 0.50 * TASA_CAMBIO },
            salsa_teriyaki: { name: "Salsa teriyaki", quantity: 800, icon: "🍯", unit: "ml", priceReduction: 0.70 * TASA_CAMBIO },
            mayonesa_japonesa: { name: "Mayonesa japonesa", quantity: 500, icon: "⚪", unit: "ml", priceReduction: 0.60 * TASA_CAMBIO },
            tempura: { name: "Rebozado tempura", quantity: 30, icon: "🍤", priceReduction: 1.50 * TASA_CAMBIO },
            sesamo: { name: "Semillas de sésamo", quantity: 200, icon: "⚫", unit: "g", priceReduction: 0.30 * TASA_CAMBIO },
            cebollin: { name: "Cebollín", quantity: 20, icon: "🧅", priceReduction: 0.40 * TASA_CAMBIO },
            aceite_sesamo: { name: "Aceite de sésamo", quantity: 300, icon: "🫒", unit: "ml", priceReduction: 0.40 * TASA_CAMBIO },
            tequila: { name: "Tequila", quantity: 40, icon: "🍶", priceReduction: 2.50 * TASA_CAMBIO },
            triple_sec: { name: "Triple sec", quantity: 30, icon: "🍊", unit: "ml", priceReduction: 1.20 * TASA_CAMBIO },
            limon: { name: "Limón", quantity: 50, icon: "🍋", priceReduction: 0.30 * TASA_CAMBIO },
            pollo: { name: "Pollo", quantity: 35, icon: "🍗", priceReduction: 2.00 * TASA_CAMBIO },
            wantan: { name: "Wantan", quantity: 60, icon: "🥟", priceReduction: 0.80 * TASA_CAMBIO },
            caldo_pollo: { name: "Caldo de pollo", quantity: 2000, icon: "🍲", unit: "ml", priceReduction: 1.00 * TASA_CAMBIO },
            edamame: { name: "Edamame", quantity: 25, icon: "🫘", priceReduction: 1.50 * TASA_CAMBIO },
            arroz_jasmin: { name: "Arroz jazmín", quantity: 3000, icon: "🍚", unit: "g", priceReduction: 1.20 * TASA_CAMBIO },
            vegetales_mixtos: { name: "Vegetales mixtos", quantity: 40, icon: "🥕", priceReduction: 1.80 * TASA_CAMBIO },
            fideos: { name: "Fideos", quantity: 20, icon: "🍜", priceReduction: 1.50 * TASA_CAMBIO },
            nuggets: { name: "Nuggets de pollo", quantity: 45, icon: "🍗", priceReduction: 1.20 * TASA_CAMBIO },
            papas: { name: "Papas fritas", quantity: 30, icon: "🍟", priceReduction: 0.80 * TASA_CAMBIO },
            jugo: { name: "Jugo", quantity: 50, icon: "🧃", unit: "ml", priceReduction: 0.50 * TASA_CAMBIO },
            langostino: { name: "Langostino", quantity: 35, icon: "🦞", priceReduction: 3.50 * TASA_CAMBIO },
            queso_crema: { name: "Queso crema", quantity: 25, icon: "🧀", priceReduction: 1.00 * TASA_CAMBIO },
            salsa_fuji: { name: "Salsa Fuji", quantity: 500, icon: "🍛", unit: "ml", priceReduction: 0.80 * TASA_CAMBIO },
            anguilla: { name: "Anguilla", quantity: 15, icon: "🐍", priceReduction: 2.00 * TASA_CAMBIO },
            ajonjoli: { name: "Ajonjolí", quantity: 150, icon: "⚫", unit: "g", priceReduction: 0.40 * TASA_CAMBIO },
            salsa_dragon: { name: "Salsa dragón", quantity: 400, icon: "🐉", unit: "ml", priceReduction: 0.90 * TASA_CAMBIO },
            cebolla_morada: { name: "Cebolla morada", quantity: 15, icon: "🧅", priceReduction: 0.50 * TASA_CAMBIO },
            aji_dulce: { name: "Ají dulce", quantity: 20, icon: "🌶️", priceReduction: 0.60 * TASA_CAMBIO },
            cilantro: { name: "Cilantro", quantity: 18, icon: "🌿", priceReduction: 0.40 * TASA_CAMBIO },
            ajimoto: { name: "Ají moto", quantity: 100, icon: "🌶️", unit: "g", priceReduction: 0.70 * TASA_CAMBIO },
            masago: { name: "Masago", quantity: 200, icon: "🐟", unit: "g", priceReduction: 1.50 * TASA_CAMBIO },
            salsa_ponzu: { name: "Salsa ponzu", quantity: 400, icon: "🍶", unit: "ml", priceReduction: 0.90 * TASA_CAMBIO },
            miso_dulce: { name: "Miso dulce", quantity: 300, icon: "🍯", unit: "ml", priceReduction: 0.80 * TASA_CAMBIO },
            almendras: { name: "Almendras", quantity: 200, icon: "🌰", unit: "g", priceReduction: 1.00 * TASA_CAMBIO },
            croquetas: { name: "Croquetas", quantity: 40, icon: "🥘", priceReduction: 0.80 * TASA_CAMBIO },
            gyosas: { name: "Gyosas", quantity: 50, icon: "🥟", priceReduction: 0.90 * TASA_CAMBIO },
            salsa_dinamita: { name: "Salsa dinamita", quantity: 350, icon: "🔥", unit: "ml", priceReduction: 0.85 * TASA_CAMBIO }
        };

        // Variable para controlar alertas de inventario bajo ya mostradas
        let lowInventoryAlertsShown = new Set();

        function convertirABs(dolares) {
            return dolares * TASA_CAMBIO;
        }

        function formatearPrecioBs(dolares) {
            const precioBs = convertirABs(dolares);
            return `Bs. ${precioBs.toFixed(2).replace('.', ',')}`;
        }

        const menuItems = [
            {
                id: 1,
                name: "Sashimi",
                category: "entradas",
                icon: "🐟",
                basePrice: 14.00,
                description: "Atún, salmón, pescado o mixto 5 piezas (20 gramos cada una).",
                ingredients: {
                    salmon: { amount: 0.4, required: false },
                    atun: { amount: 0.4, required: false },
                    pescado_blanco: { amount: 0.4, required: false },
                    wasabi: { amount: 8, required: false },
                    jengibre: { amount: 10, required: false },
                    salsa_soja: { amount: 25, required: false }
                },
                stock: 12,
                quantity: 0,
                instances: [],
                totalOrdered: 0,
                currentSelections: new Set(),
                order: 1,
                selectionType: "completo",
                imageClass: "image-sashimi"
            },
            {
                id: 2,
                name: "Coquitos de Salmón",
                category: "entradas",
                icon: "🧀",
                basePrice: 12.00,
                description: "Salmón relleno de queso crema, aguacate empanizado con topping de salsa fuji y anguilla (4 piezas).",
                ingredients: {
                    salmon: { amount: 0.5, required: true },
                    queso_crema: { amount: 0.3, required: false },
                    aguacate: { amount: 0.3, required: false },
                    salsa_fuji: { amount: 20, required: false },
                    anguilla: { amount: 0.2, required: false },
                    tempura: { amount: 0.3, required: true }
                },
                stock: 10,
                quantity: 0,
                instances: [],
                totalOrdered: 0,
                currentSelections: new Set(),
                order: 2,
                selectionType: "completo",
                imageClass: "image-coquitos"
            },
            {
                id: 3,
                name: "Festival de Langostinos",
                category: "entradas",
                icon: "🦐",
                basePrice: 12.00,
                description: "Langostinos tempurizados con salsa fuji, anguilla y lluvia de ajonjolí.",
                ingredients: {
                    langostino: { amount: 0.6, required: true },
                    tempura: { amount: 0.4, required: true },
                    salsa_fuji: { amount: 25, required: false },
                    anguilla: { amount: 0.2, required: false },
                    ajonjoli: { amount: 5, required: false },
                    salsa_soja: { amount: 15, required: false }
                },
                stock: 10,
                quantity: 0,
                instances: [],
                totalOrdered: 0,
                currentSelections: new Set(),
                order: 3,
                selectionType: "completo",
                imageClass: "image-langostinos"
            },
            {
                id: 4,
                name: "Sushi Pizza",
                category: "entradas",
                icon: "🍕",
                basePrice: 10.00,
                description: "Atún o salmón, aguacate, salsa dragón, cebollín, salsa dinamita, miso dulce y salsa anguilla.",
                ingredients: {
                    salmon: { amount: 0.3, required: false },
                    atun: { amount: 0.3, required: false },
                    aguacate: { amount: 0.4, required: false },
                    salsa_dragon: { amount: 20, required: false },
                    cebollin: { amount: 0.1, required: false },
                    salsa_dinamita: { amount: 15, required: false },
                    miso_dulce: { amount: 10, required: false },
                    anguilla: { amount: 0.1, required: false }
                },
                stock: 15,
                quantity: 0,
                instances: [],
                totalOrdered: 0,
                currentSelections: new Set(),
                order: 4,
                selectionType: "completo",
                imageClass: "image-sushi-pizza"
            },
            {
                id: 5,
                name: "Ceviche Tradicional",
                category: "entradas",
                icon: "🍋",
                basePrice: 10.00,
                description: "Cebolla morada, ají dulce, cilantro, limón, ajímoto, pescado blanco.",
                ingredients: {
                    pescado_blanco: { amount: 0.6, required: true },
                    cebolla_morada: { amount: 0.3, required: false },
                    aji_dulce: { amount: 0.2, required: false },
                    cilantro: { amount: 0.1, required: false },
                    limon: { amount: 1, required: false },
                    ajimoto: { amount: 5, required: false }
                },
                stock: 12,
                quantity: 0,
                instances: [],
                totalOrdered: 0,
                currentSelections: new Set(),
                order: 5,
                selectionType: "completo",
                imageClass: "image-ceviche"
            },
            {
                id: 6,
                name: "Ceviche Mixto",
                category: "entradas",
                icon: "🦑",
                basePrice: 14.00,
                description: "Cebolla morada, ají dulce, cilantro, limón, ajímoto, pescado blanco, langostinos y pulpo.",
                ingredients: {
                    pescado_blanco: { amount: 0.4, required: true },
                    langostino: { amount: 0.3, required: false },
                    pulpo: { amount: 0.3, required: false },
                    cebolla_morada: { amount: 0.3, required: false },
                    aji_dulce: { amount: 0.2, required: false },
                    cilantro: { amount: 0.1, required: false },
                    limon: { amount: 1, required: false },
                    ajimoto: { amount: 5, required: false }
                },
                stock: 10,
                quantity: 0,
                instances: [],
                totalOrdered: 0,
                currentSelections: new Set(),
                order: 6,
                selectionType: "completo",
                imageClass: "image-ceviche-mixto"
            },
            {
                id: 7,
                name: "Tiradito de Salmón",
                category: "entradas",
                icon: "🍣",
                basePrice: 14.00,
                description: "Salmón, aguacate, salsa ponzu, miso dulce, salsa dragón.",
                ingredients: {
                    salmon: { amount: 0.7, required: true },
                    aguacate: { amount: 0.4, required: false },
                    salsa_ponzu: { amount: 25, required: false },
                    miso_dulce: { amount: 15, required: false },
                    salsa_dragon: { amount: 15, required: false }
                },
                stock: 10,
                quantity: 0,
                instances: [],
                totalOrdered: 0,
                currentSelections: new Set(),
                order: 7,
                selectionType: "completo",
                imageClass: "image-tiradito"
            },
            {
                id: 8,
                name: "Maguro Tataki",
                category: "entradas",
                icon: "🔥",
                basePrice: 14.00,
                description: "Atún sellado con almendras, rebosado en salsa ponzu.",
                ingredients: {
                    atun: { amount: 0.8, required: true },
                    almendras: { amount: 10, required: false },
                    salsa_ponzu: { amount: 30, required: false },
                    cebollin: { amount: 0.1, required: false },
                    aceite_sesamo: { amount: 8, required: false }
                },
                stock: 8,
                quantity: 0,
                instances: [],
                totalOrdered: 0,
                currentSelections: new Set(),
                order: 8,
                selectionType: "completo",
                imageClass: "image-maguro"
            },
            {
                id: 9,
                name: "Sushi Saki Deluxe",
                category: "sushi",
                icon: "🍣",
                basePrice: 24.99,
                description: "12 piezas variadas: nigiri, maki y sashimi premium",
                ingredients: {
                    arroz_sushi: { amount: 200, required: true },
                    salmon: { amount: 0.5, required: false },
                    atun: { amount: 0.5, required: false },
                    alga_nori: { amount: 2, required: true },
                    aguacate: { amount: 0.25, required: false },
                    pepino: { amount: 0.5, required: false },
                    wasabi: { amount: 10, required: false },
                    jengibre: { amount: 15, required: false },
                    salsa_soja: { amount: 30, required: false },
                    sesamo: { amount: 5, required: false }
                },
                stock: 8,
                quantity: 0,
                instances: [],
                totalOrdered: 0,
                currentSelections: new Set(),
                order: 9,
                selectionType: "completo",
                imageClass: "image-sushi-deluxe"
            },
            {
                id: 10,
                name: "Margarita Clásica",
                category: "tragos",
                icon: "🍸",
                basePrice: 8.50,
                description: "Tequila, triple sec y jugo de limón fresco",
                ingredients: {
                    tequila: { amount: 0.5, required: true },
                    triple_sec: { amount: 15, required: false },
                    limon: { amount: 1, required: false }
                },
                stock: 20,
                quantity: 0,
                instances: [],
                totalOrdered: 0,
                currentSelections: new Set(),
                order: 10,
                selectionType: "completo",
                imageClass: "image-margarita"
            }
        ];

        const jokes = [
            "¿Seguro que quieres solo un plato vacío? 😅",
            "¡Eso es solo aire en un plato! 🍃",
            "¿Quieres que el chef te cante una canción en su lugar? 🎤",
            "¡Incluso el wasabi se sentiría solo! 🍱",
            "Prueba nuestro 'sushi de imaginación' - mismo precio! ✨",
            "¡El arroz se sentirá abandonado! 🍚"
        ];

        let jokeIndex = {};
        let currentCategory = 'todos';
        let currentSubcategory = null;

        const categoryOrder = {
            'entradas': 1,
            'sushi': 2,
            'rolls-frios': 3,
            'rolls-tempura': 4,
            'tragos': 5,
            'pokes': 6,
            'ensaladas': 7,
            'arroz-chino': 8,
            'arroz-cantones': 9,
            'chopsuey': 10,
            'lomey': 11,
            'chow-mein': 12,
            'fideos-arroz': 13,
            'tallarines-cantones': 14,
            'mariscos': 15,
            'foo-yung': 16,
            'sopas': 17,
            'entremeses': 18,
            'yakimeshi': 19,
            'yakisoba': 20,
            'pasta-udon': 21,
            'churrasco': 22,
            'ninos': 23,
            'ejecutivo': 24
        };

        function init() {
            renderMenu();
            updateOrderSummary();
            menuItems.forEach(item => {
                jokeIndex[item.id] = 0;
            });
            
            document.querySelectorAll('.category-tab').forEach(tab => {
                if (tab.textContent.includes('Todos')) {
                    tab.classList.add('active');
                }
            });
        }

        function filterCategory(category) {
            currentCategory = category;
            currentSubcategory = null;
            
            document.querySelectorAll('.category-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            event.target.classList.add('active');
            
            document.querySelectorAll('.subcategories').forEach(sub => {
                sub.style.display = 'none';
            });
            
            renderMenu();
        }

        function showSubcategories(category) {
            document.querySelectorAll('.subcategories').forEach(sub => {
                sub.style.display = 'none';
            });
            
            const subcatDiv = document.getElementById(`subcategories-${category}`);
            if (subcatDiv) {
                subcatDiv.style.display = 'flex';
            }
            
            document.querySelectorAll('.category-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            event.target.classList.add('active');
            
            currentCategory = category;
            currentSubcategory = null;
            renderMenu();
        }

        function filterSubcategory(subcategory) {
            currentSubcategory = subcategory;
            
            document.querySelectorAll('.subcategory-tab').forEach(tab => {
                tab.style.background = 'rgba(255, 255, 255, 0.15)';
            });
            event.target.style.background = 'var(--accent)';
            event.target.style.color = 'var(--secondary)';
            
            renderMenu();
        }

        function ordenarItemsPorCategoria(items) {
            return items.sort((a, b) => {
                if (a.order && b.order) {
                    return a.order - b.order;
                }
                if (a.order && !b.order) return -1;
                if (!a.order && b.order) return 1;
                
                const orderA = categoryOrder[a.category] || 99;
                const orderB = categoryOrder[b.category] || 99;
                if (orderA !== orderB) {
                    return orderA - orderB;
                }
                
                return a.name.localeCompare(b.name);
            });
        }

        function renderMenu() {
            const menuGrid = document.getElementById('menuGrid');
            
            let filteredItems = [...menuItems];
            
            if (currentCategory === 'todos') {
                filteredItems = ordenarItemsPorCategoria(filteredItems);
            } else if (currentSubcategory) {
                filteredItems = menuItems.filter(item => item.category === currentSubcategory);
            } else if (currentCategory) {
                if (currentCategory === 'sushi') {
                    filteredItems = menuItems.filter(item => 
                        item.category === 'sushi' || 
                        item.category === 'rolls-frios' || 
                        item.category === 'rolls-tempura'
                    );
                } else if (currentCategory === 'china') {
                    const subcategoriasChina = [
                        'arroz-chino', 'arroz-cantones', 'chopsuey', 'lomey', 
                        'chow-mein', 'fideos-arroz', 'tallarines-cantones', 
                        'mariscos', 'foo-yung', 'sopas', 'entremeses'
                    ];
                    filteredItems = menuItems.filter(item => 
                        subcategoriasChina.includes(item.category)
                    );
                } else if (currentCategory === 'japonesa') {
                    const subcategoriasJaponesa = [
                        'yakimeshi', 'yakisoba', 'pasta-udon', 'churrasco'
                    ];
                    filteredItems = menuItems.filter(item => 
                        subcategoriasJaponesa.includes(item.category)
                    );
                } else if (currentCategory === 'rolls') {
                    filteredItems = menuItems.filter(item => 
                        item.category === 'rolls-frios' || 
                        item.category === 'rolls-tempura'
                    );
                } else {
                    filteredItems = menuItems.filter(item => item.category === currentCategory);
                }
                
                filteredItems = ordenarItemsPorCategoria(filteredItems);
            }
            
            if (filteredItems.length === 0) {
                menuGrid.innerHTML = `
                    <div style="grid-column: 1 / -1; text-align: center; padding: 60px; color: #888; font-style: italic;">
                        <i class="fas fa-utensils" style="font-size: 4em; margin-bottom: 20px; color: var(--primary);"></i>
                        <p style="font-size: 1.4em;">Próximamente en esta categoría</p>
                        <p style="margin-top: 10px;">Estamos preparando los mejores platillos para ti</p>
                    </div>
                `;
                return;
            }
            
            menuGrid.innerHTML = '';
            
            filteredItems.forEach((item) => {
                const precioBs = formatearPrecioBs(item.basePrice);
                const menuItemDiv = document.createElement('div');
                menuItemDiv.className = 'menu-item';
                menuItemDiv.innerHTML = `
                    <div class="item-image ${item.imageClass}"></div>
                    <div class="item-header">
                        <div class="item-name">
                            <span>${item.name}</span>
                            <span class="item-price">${precioBs}</span>
                        </div>
                        <div class="item-description">${item.description}</div>
                    </div>
                    <div class="item-content">
                        <div class="quantity-section">
                            <div class="quantity-controls">
                                <button class="qty-btn" onclick="changeQuantity(${item.id}, -1)" ${item.quantity === 0 ? 'disabled' : ''}>
                                    <i class="fas fa-minus"></i>
                                </button>
                                <div class="item-quantity" id="qty-${item.id}">${item.quantity}</div>
                                <button class="qty-btn" onclick="changeQuantity(${item.id}, 1)" ${item.totalOrdered >= item.stock ? 'disabled' : ''}>
                                    <i class="fas fa-plus"></i>
                                </button>
                            </div>
                            <div class="item-stock ${getStockClass(item.stock - item.totalOrdered)}">
                                <i class="fas fa-box"></i> Disponibles: ${item.stock - item.totalOrdered} de ${item.stock}
                            </div>
                        </div>
                        
                        ${Object.keys(item.ingredients).length > 0 ? `
                        <div class="ingredients-section hidden" id="ingredients-${item.id}">
                            <div class="ingredients-title">
                                <i class="fas fa-utensils"></i>
                                <h3>Personaliza tu pedido</h3>
                            </div>
                            <div class="ingredient-options" id="options-${item.id}"></div>
                            <div class="joke-notice" id="joke-${item.id}"></div>
                            <div class="ingredient-actions">
                                <button class="confirm-btn" onclick="confirmCustomization(${item.id})" id="confirm-${item.id}" disabled>
                                    <i class="fas fa-check"></i> Confirmar Selección
                                </button>
                            </div>
                            <div class="price-adjustment" id="price-adj-${item.id}"></div>
                        </div>
                        ` : ''}
                    </div>
                `;
                menuGrid.appendChild(menuItemDiv);
                
                if (Object.keys(item.ingredients).length > 0) {
                    generateIngredientOptions(item.id);
                }
            });
        }

        function generateIngredientOptions(itemId) {
            const item = menuItems.find(i => i.id === itemId);
            const optionsDiv = document.getElementById(`options-${itemId}`);
            optionsDiv.innerHTML = '';
            
            // Primero agregar la opción "Completo" como un checkbox más
            const completeOption = document.createElement('div');
            completeOption.className = `ingredient-option complete-option ${item.selectionType === 'completo' ? 'selected' : ''}`;
            completeOption.onclick = () => selectComplete(itemId);
            
            completeOption.innerHTML = `
                <div class="ingredient-checkbox ${item.selectionType === 'completo' ? 'checked' : ''}"></div>
                <div class="ingredient-icon">✅</div>
                <div class="ingredient-name">Platillo completo (con todos los ingredientes)</div>
            `;
            optionsDiv.appendChild(completeOption);
            
            // Luego agregar las opciones para quitar ingredientes
            Object.keys(item.ingredients).forEach(ingredientKey => {
                const ingredient = item.ingredients[ingredientKey];
                if (!ingredient.required) {
                    const ingOption = document.createElement('div');
                    ingOption.className = 'ingredient-option';
                    ingOption.onclick = () => toggleIngredient(itemId, ingredientKey);
                    
                    const isSelected = item.currentSelections.has(ingredientKey);
                    
                    ingOption.innerHTML = `
                        <div class="ingredient-checkbox ${isSelected ? 'checked' : ''}"></div>
                        <div class="ingredient-icon">${inventory[ingredientKey].icon}</div>
                        <div class="ingredient-name">Sin ${inventory[ingredientKey].name.toLowerCase()}</div>
                    `;
                    optionsDiv.appendChild(ingOption);
                }
            });
        }

        function selectComplete(itemId) {
            const item = menuItems.find(i => i.id === itemId);
            item.selectionType = "completo";
            item.currentSelections.clear();
            
            generateIngredientOptions(itemId);
            updateConfirmButton(itemId);
        }

        function toggleIngredient(itemId, ingredientKey) {
            const item = menuItems.find(i => i.id === itemId);
            item.selectionType = "personalizado";
            
            if (item.currentSelections.has(ingredientKey)) {
                item.currentSelections.delete(ingredientKey);
            } else {
                item.currentSelections.add(ingredientKey);
            }
            
            generateIngredientOptions(itemId);
            updateConfirmButton(itemId);
        }

        function changeQuantity(itemId, change) {
            const item = menuItems.find(i => i.id === itemId);
            const newQty = item.quantity + change;
            
            if (newQty < 0) return;
            
            const availableStock = item.stock - item.totalOrdered;
            
            if (change > 0) {
                if (availableStock <= 0) {
                    showMaxReachedNotice(item.name, item.totalOrdered);
                    return;
                }
                
                if (newQty > availableStock) {
                    item.quantity = availableStock;
                    showMaxReachedNotice(item.name, item.stock);
                } else {
                    item.quantity = newQty;
                }
            } else {
                item.quantity = newQty;
            }
            
            document.getElementById(`qty-${itemId}`).textContent = item.quantity;
            
            // Actualizar botones de cantidad en todas las categorías
            updateQuantityButtons(itemId);
            
            const ingredientsSection = document.getElementById(`ingredients-${itemId}`);
            if (ingredientsSection) {
                if (item.quantity > 0) {
                    setTimeout(() => {
                        ingredientsSection.classList.remove('hidden');
                    }, 10);
                    
                    if (change > 0) {
                        item.instances.push({
                            id: item.instances.length + 1,
                            removedIngredients: [],
                            isComplete: true,
                            price: convertirABs(item.basePrice),
                            selectionType: item.selectionType
                        });
                    }
                    else if (change < 0 && item.instances.length > 0) {
                        item.instances.pop();
                    }
                } else {
                    ingredientsSection.classList.add('hidden');
                    item.instances = [];
                    item.currentSelections.clear();
                    item.selectionType = "completo";
                    generateIngredientOptions(itemId);
                }
            } else {
                if (item.quantity > 0 && change > 0) {
                    item.instances.push({
                        id: item.instances.length + 1,
                        removedIngredients: [],
                        isComplete: true,
                        price: convertirABs(item.basePrice),
                        selectionType: "completo"
                    });
                }
                else if (change < 0 && item.instances.length > 0) {
                    item.instances.pop();
                }
            }
            
            // Actualizar stock display en todas las categorías
            updateStockDisplay(itemId);
            
            updateOrderSummary();
        }

        function updateQuantityButtons(itemId) {
            const item = menuItems.find(i => i.id === itemId);
            
            // Buscar todos los elementos de este item en la vista actual
            const allQuantityControls = document.querySelectorAll(`.menu-item:nth-child(${itemId}) .quantity-controls`);
            
            allQuantityControls.forEach(controls => {
                const minusBtn = controls.querySelector('.qty-btn:first-child');
                const plusBtn = controls.querySelector('.qty-btn:last-child');
                
                if (minusBtn) minusBtn.disabled = item.quantity === 0;
                if (plusBtn) plusBtn.disabled = (item.totalOrdered + item.quantity) >= item.stock;
            });
        }

        function updateStockDisplay(itemId) {
            const item = menuItems.find(i => i.id === itemId);
            const availableStock = item.stock - item.totalOrdered;
            const stockClass = getStockClass(availableStock);
            
            // Buscar todos los elementos de stock de este item
            const allStockDisplays = document.querySelectorAll(`.menu-item:nth-child(${itemId}) .item-stock`);
            
            allStockDisplays.forEach(stockDisplay => {
                stockDisplay.className = `item-stock ${stockClass}`;
                stockDisplay.innerHTML = `<i class="fas fa-box"></i> Disponibles: ${availableStock} de ${item.stock}`;
            });
        }

        function showMaxReachedNotice(itemName, quantity) {
            document.getElementById('maxQuantity').textContent = quantity;
            document.getElementById('maxReachedNotice').style.display = 'block';
            document.getElementById('overlay').style.display = 'block';
        }

        function closeMaxNotice() {
            document.getElementById('maxReachedNotice').style.display = 'none';
            document.getElementById('overlay').style.display = 'none';
        }

        function confirmCustomization(itemId) {
            const item = menuItems.find(i => i.id === itemId);
            
            if (item.instances.length === 0) return;
            
            const currentInstance = item.instances[item.instances.length - 1];
            const allNonRequired = Object.keys(item.ingredients).filter(key => !item.ingredients[key].required);
            
            // Si es personalizado, verificar que no se quitaron todos
            if (item.selectionType === "personalizado") {
                if (item.currentSelections.size === allNonRequired.length) {
                    alert("¡No puedes quitar todos los ingredientes! Por favor, deja al menos uno.");
                    return;
                }
            }
            
            const selectedIngredients = Array.from(item.currentSelections);
            let totalReduction = 0;
            
            selectedIngredients.forEach(ingredientKey => {
                totalReduction += (inventory[ingredientKey].priceReduction || 0);
            });
            
            // Actualizar instancia
            currentInstance.removedIngredients = selectedIngredients;
            currentInstance.isComplete = selectedIngredients.length === 0;
            currentInstance.price = selectedIngredients.length > 0 
                ? Math.max(convertirABs(item.basePrice) - totalReduction, convertirABs(item.basePrice) * 0.4)
                : convertirABs(item.basePrice);
            currentInstance.selectionType = item.selectionType;
            
            // Resetear contador y plegar sección
            item.totalOrdered += item.quantity;
            item.quantity = 0;
            
            // Limpiar selecciones actuales y volver a "completo" por defecto
            item.currentSelections.clear();
            item.selectionType = "completo";
            
            // Actualizar UI - Primero ocultar la sección con transición suave
            const ingredientsSection = document.getElementById(`ingredients-${itemId}`);
            if (ingredientsSection) {
                ingredientsSection.classList.add('hidden');
            }
            
            setTimeout(() => {
                document.getElementById(`qty-${itemId}`).textContent = '0';
                const confirmBtn = document.getElementById(`confirm-${itemId}`);
                if (confirmBtn) confirmBtn.disabled = true;
                const priceAdjDiv = document.getElementById(`price-adj-${itemId}`);
                if (priceAdjDiv) priceAdjDiv.style.display = 'none';
                const jokeDiv = document.getElementById(`joke-${itemId}`);
                if (jokeDiv) jokeDiv.style.display = 'none';
                
                // Actualizar botones de cantidad y stock en todas las vistas
                updateQuantityButtons(itemId);
                updateStockDisplay(itemId);
                
                // Actualizar UI de ingredientes
                generateIngredientOptions(itemId);
                
                updateOrderSummary();
            }, 500);
        }

        function updateConfirmButton(itemId) {
            const item = menuItems.find(i => i.id === itemId);
            const confirmBtn = document.getElementById(`confirm-${itemId}`);
            const priceAdjDiv = document.getElementById(`price-adj-${itemId}`);
            
            if (item.instances.length === 0) {
                if (confirmBtn) confirmBtn.disabled = true;
                return;
            }
            
            const allNonRequired = Object.keys(item.ingredients).filter(key => !item.ingredients[key].required);
            
            if (item.selectionType === "personalizado") {
                const allSelected = allNonRequired.length > 0 && item.currentSelections.size === allNonRequired.length;
                
                if (allSelected) {
                    if (confirmBtn) confirmBtn.disabled = true;
                    if (priceAdjDiv) priceAdjDiv.style.display = 'none';
                } else {
                    if (confirmBtn) confirmBtn.disabled = false;
                    
                    if (item.currentSelections.size > 0) {
                        let totalReduction = 0;
                        item.currentSelections.forEach(ingredientKey => {
                            totalReduction += (inventory[ingredientKey].priceReduction || 0);
                        });
                        const newPrice = Math.max(convertirABs(item.basePrice) - totalReduction, convertirABs(item.basePrice) * 0.4);
                        if (priceAdjDiv) {
                            priceAdjDiv.innerHTML = `<i class="fas fa-tag"></i> Nuevo precio: <strong>Bs. ${newPrice.toFixed(2).replace('.', ',')}</strong> (Bs. ${totalReduction.toFixed(2).replace('.', ',')} menos)`;
                            priceAdjDiv.style.display = 'block';
                        }
                    } else {
                        if (priceAdjDiv) {
                            priceAdjDiv.innerHTML = `<i class="fas fa-tag"></i> Precio completo: <strong>${formatearPrecioBs(item.basePrice)}</strong>`;
                            priceAdjDiv.style.display = 'block';
                        }
                    }
                }
            } else {
                // Para selección "completa"
                if (confirmBtn) confirmBtn.disabled = false;
                if (priceAdjDiv) {
                    priceAdjDiv.innerHTML = `<i class="fas fa-tag"></i> Precio completo: <strong>${formatearPrecioBs(item.basePrice)}</strong>`;
                    priceAdjDiv.style.display = 'block';
                }
            }
        }

        function getStockClass(stock) {
            if (stock === 0) return 'sold-out';
            if (stock <= 2) return 'low';
            return 'available';
        }

        function updateOrderSummary() {
            const orderSummaryContent = document.getElementById('orderSummaryContent');
            const orderBtn = document.getElementById('orderBtn');
            
            const validItems = menuItems.filter(item => {
                return item.instances.some(instance => {
                    if (Object.keys(item.ingredients).length > 0) {
                        const allNonRequired = Object.keys(item.ingredients).filter(key => !item.ingredients[key].required);
                        return instance.removedIngredients.length < allNonRequired.length;
                    }
                    return true;
                });
            });
            
            if (validItems.length === 0) {
                orderSummaryContent.innerHTML = `
                    <div class="empty-summary" style="text-align: center; padding: 40px; color: #888; font-style: italic;">
                        <i class="fas fa-sushi-roll" style="font-size: 3em; margin-bottom: 20px; color: var(--primary);"></i>
                        <p style="font-size: 1.2em;">Aún no has seleccionado ningún platillo</p>
                        <p style="margin-top: 10px;">Usa los botones + para comenzar tu pedido</p>
                    </div>
                `;
                orderBtn.disabled = true;
                return;
            }
            
            let html = '<div class="order-grid">';
            let total = 0;
            let totalItems = 0;
            
            validItems.forEach(item => {
                const validInstances = item.instances.filter(instance => {
                    if (Object.keys(item.ingredients).length > 0) {
                        const allNonRequired = Object.keys(item.ingredients).filter(key => !item.ingredients[key].required);
                        return instance.removedIngredients.length < allNonRequired.length;
                    }
                    return true;
                });
                
                if (validInstances.length === 0) return;
                
                html += `<div class="order-item-card">`;
                html += `<div class="instance-number">${validInstances.length}</div>`;
                
                validInstances.forEach((instance, index) => {
                    total += instance.price;
                    totalItems++;
                    
                    let modifiers = '';
                    if (instance.removedIngredients.length > 0) {
                        modifiers = 'Personalizado (sin: ';
                        instance.removedIngredients.forEach((ingredientKey, idx) => {
                            modifiers += inventory[ingredientKey].name.toLowerCase();
                            if (idx < instance.removedIngredients.length - 1) {
                                modifiers += ', ';
                            }
                        });
                        modifiers += ')';
                    } else {
                        modifiers = 'Completo (todos los ingredientes)';
                    }
                    
                    html += `
                        <div class="item-instance">
                            <div class="order-item-info">
                                <div class="order-item-details">
                                    <div class="order-item-name">
                                        <i class="fas fa-utensils"></i>
                                        ${item.name} #${index + 1}
                                    </div>
                                    <div class="order-item-modifiers">${modifiers}</div>
                                </div>
                                <div class="order-item-price">Bs. ${instance.price.toFixed(2).replace('.', ',')}</div>
                            </div>
                        </div>
                    `;
                });
                
                html += `</div>`;
            });
            
            html += '</div>';
            
            html += `
                <div class="summary-total-items">
                    <div><i class="fas fa-receipt"></i> ${totalItems} platillo${totalItems !== 1 ? 's' : ''}</div>
                    <div class="items-total">Total: Bs. ${total.toFixed(2).replace('.', ',')}</div>
                </div>
            `;
            
            orderSummaryContent.innerHTML = html;
            orderBtn.disabled = false;
        }

        function calculateMaxPossibleItems(item) {
            let maxItems = item.stock;
            
            for (const [ingredientKey, ingredient] of Object.entries(item.ingredients)) {
                const available = inventory[ingredientKey].quantity;
                const neededPerItem = ingredient.amount;
                
                if (neededPerItem > 0) {
                    const maxFromThisIngredient = Math.floor(available / neededPerItem);
                    maxItems = Math.min(maxItems, maxFromThisIngredient);
                }
            }
            
            return Math.max(0, maxItems);
        }

        function placeOrder() {
            const validItems = menuItems.filter(item => {
                return item.instances.some(instance => {
                    if (Object.keys(item.ingredients).length > 0) {
                        const allNonRequired = Object.keys(item.ingredients).filter(key => !item.ingredients[key].required);
                        return instance.removedIngredients.length < allNonRequired.length;
                    }
                    return true;
                });
            });
            
            if (validItems.length === 0) {
                alert('¡No tienes platillos válidos en tu pedido!');
                return;
            }
            
            const inventoryCheck = checkInventory(validItems);
            if (!inventoryCheck.canProcess) {
                showInventoryError(validItems, inventoryCheck.maxPossible);
                return;
            }
            
            showOrderConfirmation(validItems);
            updateInventory(validItems);
            
            // Resetear el conjunto de alertas mostradas para el próximo pedido
            lowInventoryAlertsShown.clear();
            
            const lowInventoryItems = checkLowInventory(validItems);
            
            // Limpiar todas las instancias de pedidos
            menuItems.forEach(item => {
                item.instances = [];
                item.quantity = 0;
                item.totalOrdered = 0;
                item.currentSelections.clear();
                item.selectionType = "completo";
                
                // Forzar actualización de UI en todas las vistas
                document.getElementById(`qty-${item.id}`).textContent = '0';
                
                // Actualizar botones de cantidad y stock en todas las vistas
                updateQuantityButtons(item.id);
                updateStockDisplay(item.id);
                
                // Actualizar UI de ingredientes si el item está visible
                const ingredientsSection = document.getElementById(`ingredients-${item.id}`);
                if (ingredientsSection) {
                    ingredientsSection.classList.add('hidden');
                    generateIngredientOptions(item.id);
                }
            });
            
            // Forzar re-renderizado del menú
            renderMenu();
            updateOrderSummary();
            
            document.getElementById('thankYouMessage').style.display = 'block';
            
            setTimeout(() => {
                if (lowInventoryItems.length > 0) {
                    showInventoryAlert(lowInventoryItems);
                }
            }, 1500);
        }

        function checkInventory(validItems) {
            const result = {
                canProcess: true,
                maxPossible: {},
                insufficientIngredients: []
            };
            
            // Calcular cuántos de cada platillo se pueden hacer con el inventario actual
            validItems.forEach(item => {
                const itemInstances = item.instances.filter(instance => {
                    if (Object.keys(item.ingredients).length > 0) {
                        const allNonRequired = Object.keys(item.ingredients).filter(key => !item.ingredients[key].required);
                        return instance.removedIngredients.length < allNonRequired.length;
                    }
                    return true;
                });
                
                if (itemInstances.length === 0) return;
                
                const maxPossible = calculateMaxPossibleItems(item);
                result.maxPossible[item.id] = maxPossible;
                
                if (itemInstances.length > maxPossible) {
                    result.canProcess = false;
                    
                    // Identificar ingredientes insuficientes
                    for (const [ingredientKey, ingredient] of Object.entries(item.ingredients)) {
                        const available = inventory[ingredientKey].quantity;
                        const neededPerItem = ingredient.amount;
                        const totalNeeded = itemInstances.length * neededPerItem;
                        
                        if (totalNeeded > available) {
                            result.insufficientIngredients.push({
                                itemName: item.name,
                                ingredientName: inventory[ingredientKey].name,
                                available: available,
                                needed: totalNeeded,
                                shortBy: totalNeeded - available
                            });
                        }
                    }
                }
            });
            
            return result;
        }

        function showInventoryError(validItems, maxPossible) {
            const inventoryError = document.getElementById('inventoryError');
            const errorContent = document.getElementById('inventoryErrorContent');
            const maxPossibleOrder = document.getElementById('maxPossibleOrder');
            const overlay = document.getElementById('overlay');
            
            let html = '<p style="margin-bottom: 20px; color: #666; font-size: 1.1em;">No tenemos suficiente inventario para tu pedido completo:</p>';
            
            validItems.forEach(item => {
                const itemInstances = item.instances.filter(instance => {
                    if (Object.keys(item.ingredients).length > 0) {
                        const allNonRequired = Object.keys(item.ingredients).filter(key => !item.ingredients[key].required);
                        return instance.removedIngredients.length < allNonRequired.length;
                    }
                    return true;
                });
                
                if (itemInstances.length === 0) return;
                
                const maxForThisItem = maxPossible[item.id] || 0;
                
                if (itemInstances.length > maxForThisItem) {
                    html += `
                        <div style="margin-bottom: 15px; padding-bottom: 15px; border-bottom: 1px solid #E0E0E0;">
                            <div style="font-weight: bold; color: var(--primary); margin-bottom: 5px;">${item.name}</div>
                            <div style="font-size: 0.9em; color: #666;">
                                Pediste: ${itemInstances.length} unidades<br>
                                Máximo posible: ${maxForThisItem} unidades
                            </div>
                        </div>
                    `;
                }
            });
            
            // Construir mensaje de cantidad máxima posible
            let maxOrderMessage = 'Cantidad máxima que puedes ordenar: ';
            let first = true;
            
            validItems.forEach(item => {
                const maxForThisItem = maxPossible[item.id] || 0;
                if (maxForThisItem > 0) {
                    if (!first) maxOrderMessage += ', ';
                    maxOrderMessage += `${maxForThisItem} de ${item.name}`;
                    first = false;
                }
            });
            
            if (!first) {
                maxPossibleOrder.textContent = maxOrderMessage;
                maxPossibleOrder.style.display = 'block';
            } else {
                maxPossibleOrder.style.display = 'none';
            }
            
            errorContent.innerHTML = html;
            inventoryError.style.display = 'block';
            overlay.style.display = 'block';
        }

        function closeInventoryError() {
            document.getElementById('inventoryError').style.display = 'none';
            document.getElementById('overlay').style.display = 'none';
        }

        function updateInventory(validItems) {
            validItems.forEach(item => {
                item.instances.forEach(instance => {
                    const allNonRequired = Object.keys(item.ingredients).filter(key => !item.ingredients[key].required);
                    if (instance.removedIngredients.length >= allNonRequired.length) return;
                    
                    for (const [ingredientKey, ingredient] of Object.entries(item.ingredients)) {
                        if (!instance.removedIngredients.includes(ingredientKey)) {
                            inventory[ingredientKey].quantity = Math.round((inventory[ingredientKey].quantity - ingredient.amount) * 100) / 100;
                        }
                    }
                });
            });
        }

        function checkLowInventory(orderedItems) {
            const lowInventoryItems = [];
            const usedIngredients = new Set();
            
            // Primero, identificar qué ingredientes se usaron en este pedido
            orderedItems.forEach(item => {
                item.instances.forEach(instance => {
                    const allNonRequired = Object.keys(item.ingredients).filter(key => !item.ingredients[key].required);
                    if (instance.removedIngredients.length >= allNonRequired.length) return;
                    
                    for (const ingredientKey of Object.keys(item.ingredients)) {
                        if (!instance.removedIngredients.includes(ingredientKey)) {
                            usedIngredients.add(ingredientKey);
                        }
                    }
                });
            });
            
            // Solo verificar inventario bajo para ingredientes usados
            for (const [key, ingredient] of Object.entries(inventory)) {
                if (usedIngredients.has(key)) {
                    if (!ingredient.unit) {
                        if (ingredient.quantity <= 5 && ingredient.quantity > 0 && !lowInventoryAlertsShown.has(key)) {
                            lowInventoryItems.push({
                                key: key,
                                name: ingredient.name,
                                icon: ingredient.icon,
                                quantity: ingredient.quantity,
                                unit: ingredient.unit || 'unidades'
                            });
                            lowInventoryAlertsShown.add(key);
                        }
                    } else if (ingredient.quantity <= 100 && !lowInventoryAlertsShown.has(key)) {
                        lowInventoryItems.push({
                            key: key,
                            name: ingredient.name,
                            icon: ingredient.icon,
                            quantity: ingredient.quantity,
                            unit: ingredient.unit
                        });
                        lowInventoryAlertsShown.add(key);
                    }
                }
            }
            
            return lowInventoryItems;
        }

        function showInventoryAlert(lowInventoryItems) {
            if (lowInventoryItems.length === 0) return;
            
            const alertContent = document.getElementById('alertContent');
            const inventoryAlert = document.getElementById('inventoryAlert');
            const overlay = document.getElementById('overlay');
            
            let html = '<p style="margin-bottom: 20px; color: #666; font-size: 1.1em;">Los siguientes ingredientes están bajos:</p>';
            
            lowInventoryItems.forEach(item => {
                html += `
                    <div style="display: flex; justify-content: space-between; align-items: center; padding: 12px 0; border-bottom: 1px solid #FFE0B2;">
                        <div style="display: flex; align-items: center; gap: 10px;">
                            <div style="font-size: 1.3em;">${item.icon}</div>
                            <div>${item.name}</div>
                        </div>
                        <div style="font-weight: bold; color: #D84315;">${item.quantity} ${item.unit}</div>
                    </div>
                `;
            });
            
            html += '<p style="margin-top: 20px; color: #D84315; font-weight: bold; font-size: 1.1em;"><i class="fas fa-exclamation-circle"></i> Sería prudente comprar más.</p>';
            
            alertContent.innerHTML = html;
            inventoryAlert.style.display = 'block';
            overlay.style.display = 'block';
            
            setTimeout(() => {
                if (inventoryAlert.style.display === 'block') {
                    closeInventoryAlert();
                }
            }, 10000);
        }

        function closeInventoryAlert() {
            document.getElementById('inventoryAlert').style.display = 'none';
            document.getElementById('overlay').style.display = 'none';
        }

        function showOrderConfirmation(validItems) {
            const notification = document.getElementById('notification');
            const orderDetails = document.getElementById('orderDetails');
            const overlay = document.getElementById('overlay');
            const orderTotalPrice = document.getElementById('orderTotalPrice');
            
            let total = 0;
            let html = '';
            
            validItems.forEach(item => {
                const validInstances = item.instances.filter(instance => {
                    if (Object.keys(item.ingredients).length > 0) {
                        const allNonRequired = Object.keys(item.ingredients).filter(key => !item.ingredients[key].required);
                        return instance.removedIngredients.length < allNonRequired.length;
                    }
                    return true;
                });
                
                validInstances.forEach((instance, index) => {
                    total += instance.price;
                    
                    let modifiers = '';
                    if (instance.removedIngredients.length > 0) {
                        modifiers = ' (personalizado, sin: ';
                        instance.removedIngredients.forEach((ingredientKey, idx) => {
                            modifiers += inventory[ingredientKey].name.toLowerCase();
                            if (idx < instance.removedIngredients.length - 1) {
                                modifiers += ', ';
                            }
                        });
                        modifiers += ')';
                    } else {
                        modifiers = ' (completo)';
                    }
                    
                    html += `
                        <div style="display: flex; justify-content: space-between; align-items: center; padding: 15px 0; border-bottom: 1px solid #E0E0E0;">
                            <div style="display: flex; align-items: center; gap: 15px;">
                                <div style="font-size: 1.5em;">${item.icon}</div>
                                <div>
                                    <div style="font-weight: bold;">${item.name} #${index + 1}</div>
                                    <div style="font-size: 0.9em; color: #666;">${modifiers}</div>
                                </div>
                            </div>
                            <div style="font-weight: bold; color: var(--primary);">Bs. ${instance.price.toFixed(2).replace('.', ',')}</div>
                        </div>
                    `;
                });
            });
            
            orderDetails.innerHTML = html;
            orderTotalPrice.textContent = `Bs. ${total.toFixed(2).replace('.', ',')}`;
            
            notification.style.display = 'block';
            overlay.style.display = 'block';
        }

        function closeNotification() {
            document.getElementById('notification').style.display = 'none';
            document.getElementById('overlay').style.display = 'none';
        }

        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>