- 👋 Hi, I’m @agnez47
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
agnez47/agnez47 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chatbot Pakaian dalam Konteks Sosial Budaya</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        #chat-container {
            border: 1px solid #ccc;
            padding: 10px;
            height: 400px;
            overflow-y: scroll;
        }
        #user-input {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
        }
        #send-button {
            display: block;
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Chatbot Pakaian dalam Konteks Sosial Budaya</h1>
    <div id="chat-container"></div>
    <input type="text" id="user-input" placeholder="Tanyakan sesuatu...">
    <button id="send-button">Kirim</button>

    <script>
        const chatContainer = document.getElementById('chat-container');
        const userInput = document.getElementById('user-input');
        const sendButton = document.getElementById('send-button');

        const pakaianInfo = {
            jakarta: "Jakarta sebagai ibukota cenderung lebih formal. Untuk pekerjaan, jas dan kemeja untuk pria, blazer dan rok/celana panjang untuk wanita umum digunakan. Untuk acara non-formal, pakaian casual tetap rapi.",
            bogor: "Bogor memiliki suhu yang lebih sejuk. Pakaian berlapis seperti cardigan atau jaket ringan cocok digunakan. Untuk acara formal, tetap gunakan pakaian formal namun dengan bahan yang nyaman.",
            depok: "Depok memiliki gaya yang lebih santai. Pakaian kasual seperti jeans dan kaos populer untuk kegiatan sehari-hari. Untuk acara formal, tetap gunakan pakaian formal standar.",
            tangerang: "Tangerang memiliki campuran gaya modern dan tradisional. Pakaian kasual modern populer untuk kegiatan sehari-hari. Acara formal mengikuti standar Jakarta.",
            bekasi: "Bekasi memiliki gaya yang mirip dengan Jakarta namun sedikit lebih santai. Pakaian smart casual populer untuk kegiatan sehari-hari. Acara formal tetap mengikuti standar Jakarta.",
            formal: "Acara formal umumnya memerlukan pakaian resmi seperti jas dan dasi untuk pria, gaun atau setelan blazer untuk wanita. Hindari pakaian terlalu terbuka atau casual.",
            nonformal: "Acara non-formal lebih fleksibel. Pakaian casual seperti jeans, kaos, atau kemeja santai bisa digunakan. Pastikan tetap rapi dan sesuai dengan jenis acara.",
            warna: {
                hitam: "Warna hitam cocok untuk acara formal, memberikan kesan elegan dan profesional.",
                putih: "Warna putih melambangkan kesucian dan kebersihan, cocok untuk berbagai acara.",
                merah: "Warna merah menarik perhatian, cocok untuk acara pesta atau perayaan.",
                biru: "Warna biru memberikan kesan tenang dan profesional, cocok untuk lingkungan kerja.",
                hijau: "Warna hijau melambangkan kesegaran, cocok untuk acara outdoor atau casual."
            },
            jenis: {
                kemeja: "Kemeja adalah pilihan versatil untuk pria dan wanita, cocok untuk acara formal maupun casual.",
                gaun: "Gaun cocok untuk wanita di berbagai acara, dari formal hingga pesta.",
                jas: "Jas memberikan kesan formal dan profesional, cocok untuk acara bisnis atau pesta resmi.",
                kaos: "Kaos adalah pilihan casual yang nyaman, cocok untuk kegiatan sehari-hari atau acara santai."
            },
            model: {
                tradisional: "Model tradisional seperti batik atau kebaya cocok untuk acara formal atau budaya.",
                modern: "Model modern seperti dress minimalis atau setelan jas slim fit populer untuk acara formal kontemporer.",
                casual: "Model casual seperti jeans dan t-shirt cocok untuk kegiatan sehari-hari atau acara santai."
            },
            pesta: "Untuk pesta, pilih pakaian yang sesuai dengan tema. Gaun cocktail atau kemeja dengan celana bahan untuk pria biasanya cocok. Perhatikan dress code yang mungkin ditentukan.",
            ibadah: "Untuk ke tempat ibadah, pilih pakaian yang sopan dan tertutup. Hindari pakaian yang terlalu ketat atau terbuka. Untuk masjid, wanita disarankan menggunakan jilbab."
        };

        function botResponse(input) {
            input = input.toLowerCase();
            let response = "";

            if (input.includes('jakarta') || input.includes('bogor') || input.includes('depok') || 
                input.includes('tangerang') || input.includes('bekasi')) {
                for (let city in pakaianInfo) {
                    if (input.includes(city)) {
                        response += pakaianInfo[city] + " ";
                    }
                }
            } else if (input.includes('formal')) {
                response = pakaianInfo.formal;
            } else if (input.includes('non-formal') || input.includes('nonformal')) {
                response = pakaianInfo.nonformal;
            } else if (input.includes('warna')) {
                for (let color in pakaianInfo.warna) {
                    if (input.includes(color)) {
                        response += pakaianInfo.warna[color] + " ";
                    }
                }
                if (response === "") {
                    response = "Warna pakaian dapat mempengaruhi kesan yang Anda berikan. Misalnya, hitam untuk kesan formal, putih untuk kesan bersih, merah untuk menarik perhatian, biru untuk kesan profesional, dan hijau untuk kesan segar.";
                }
            } else if (input.includes('jenis')) {
                for (let type in pakaianInfo.jenis) {
                    if (input.includes(type)) {
                        response += pakaianInfo.jenis[type] + " ";
                    }
                }
                if (response === "") {
                    response = "Ada berbagai jenis pakaian seperti kemeja, gaun, jas, dan kaos. Masing-masing cocok untuk situasi yang berbeda.";
                }
            } else if (input.includes('model')) {
                for (let style in pakaianInfo.model) {
                    if (input.includes(style)) {
                        response += pakaianInfo.model[style] + " ";
                    }
                }
                if (response === "") {
                    response = "Model pakaian bisa tradisional, modern, atau casual. Pilihlah sesuai dengan acara dan preferensi pribadi Anda.";
                }
            } else if (input.includes('pesta')) {
                response = pakaianInfo.pesta;
            } else if (input.includes('ibadah')) {
                response = pakaianInfo.ibadah;
            } else if (input.includes('pakaian') || input.includes('busana')) {
                response = "Pakaian memiliki peran penting dalam konteks sosial budaya. Pemilihan pakaian dapat mencerminkan identitas, status sosial, dan menunjukkan rasa hormat terhadap acara atau lingkungan tertentu. Anda bisa bertanya lebih spesifik tentang kota, jenis acara, warna, jenis pakaian, atau model pakaian.";
            } else {
                response = "Maaf, saya tidak memahami pertanyaan Anda. Bisa Anda tanyakan tentang pakaian di kota tertentu di JABODETABEK, acara formal/non-formal, warna pakaian, jenis pakaian, model pakaian, atau pakaian untuk acara khusus seperti pesta atau ke tempat ibadah?";
            }

            return response;
        }

        function addMessage(sender, message) {
            const messageElement = document.createElement('p');
            messageElement.innerHTML = `<strong>${sender}:</strong> ${message}`;
            chatContainer.appendChild(messageElement);
            chatContainer.scrollTop = chatContainer.scrollHeight;
        }

        function handleUserInput() {
            const userMessage = userInput.value.trim();
            if (userMessage) {
                addMessage('Anda', userMessage);
                const botMessage = botResponse(userMessage);
                setTimeout(() => addMessage('Bot', botMessage), 500);
                userInput.value = '';
            }
        }

        sendButton.addEventListener('click', handleUserInput);
        userInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                handleUserInput();
            }
        });

        // Pesan pembuka
        addMessage('Bot', 'Halo! Saya adalah chatbot yang bisa membantu Anda dengan informasi tentang pakaian dalam konteks sosial budaya. Anda bisa bertanya tentang pakaian di kota-kota JABODETABEK, acara formal/non-formal, warna pakaian, jenis pakaian, model pakaian, atau pakaian untuk acara khusus seperti pesta atau ke tempat ibadah. Apa yang ingin Anda ketahui?');
    </script>
</body>
</html>
