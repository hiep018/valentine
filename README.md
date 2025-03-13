
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ngày 14-3 - Ngày Lễ Tình Nhân</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #001f2d; /* Màu nền tối */
            text-align: center;
            color: #ff4d6d;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            overflow: hidden;
        }

        .gift-box {
            font-size: 120px;
            color: red;
            cursor: pointer;
            transition: transform 1s, font-size 1s;
        }

        .gift-box.opened {
            transform: scale(1.33); /* Hộp quà phóng to khi mở */
            font-size: 140px;
        }

        .message {
            font-size: 30px;
            margin-top: 20px;
            opacity: 0;
            transition: opacity 2s 1s; /* Tin nhắn sẽ hiện sau khi mở hộp */
        }

        .message.show {
            opacity: 1;
        }

        .heart {
            position: absolute;
            top: -10px;
            color: red;
            font-size: 20px;
            user-select: none;
            pointer-events: none;
            animation: fall 10s linear infinite;
        }

        /* Tạo hiệu ứng trái tim rơi */
        @keyframes fall {
            to {
                transform: translateY(100vh);
            }
        }
    </style>
</head>
<body>

    <!-- Hộp quà -->
    <div class="gift-box" id="giftBox">🎁</div>

    <!-- Tin nhắn -->
    <div class="message" id="message">
        Chúc em một Ngày Lễ Tình Nhân thật ngọt ngào và đầy yêu thương! <br>
        <span>14-3, Ngày Của Chúng Ta!</span>
    </div>

    <!-- Hiệu ứng trái tim rơi -->
    <script>
        const heartsCount = 50; // Số lượng trái tim
        const heartsContainer = document.body;

        // Tạo hiệu ứng trái tim rơi
        for (let i = 0; i < heartsCount; i++) {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.textContent = '❤️'; // Biểu tượng trái tim
            heart.style.left = ${Math.random() * 100}vw; // Vị trí ngẫu nhiên trên chiều ngang
            heart.style.animationDuration = ${Math.random() * 5 + 5}s; // Thời gian rơi ngẫu nhiên
            heartsContainer.appendChild(heart);
        }

        // Lắng nghe sự kiện click vào hộp quà
        document.getElementById('giftBox').addEventListener('click', function() {
            // Thêm class mở hộp quà
            this.classList.add('opened');
            // Hiển thị tin nhắn
            document.getElementById('message').classList.add('show');
        });
    </script>

</body>
</html>
