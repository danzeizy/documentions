Oke, aku gabungkan semuanya jadi satu file dengan keterangan lengkap di setiap bagian. Aku format dalam Markdown biar langsung bisa di-push ke GitHub dengan tampilan yang rapi dan profesional! 😎🔥


---

# 🚀 WhatsApp Bot - List Button dan Pengiriman File

## **📌 List Button yang Tersedia**

---

### **1. Button List (Single Select)**
> Button ini digunakan untuk menampilkan list pilihan.  
> Maksimal **1 list** dengan **10 item** dalam satu pesan.  

```javascript
const buttons = [
    {
        name: "single_select",
        params: `{
            "title": "Pilih Opsi",
            "sections": [
                {
                    "menu": ".menu",
                    "highlight_label": "Label",
                    "rows": [
                        {
                            "header": "Header 1",
                            "title": "Opsi 1",
                            "description": "Deskripsi Opsi 1",
                            "id": "id1"
                        },
                        {
                            "header": "Header 2",
                            "title": "Opsi 2",
                            "description": "Deskripsi Opsi 2",
                            "id": "id2"
                        }
                    ]
                }
            ]
        }`
    }
];


---

2. Quick Reply

> Tombol ini memungkinkan pengguna untuk membalas pesan dengan cepat.
Maksimal 3 quick reply dalam satu pesan.



const buttons = [
    {
        name: "cta_reply",
        params: `{"display_text":"Quick Reply","id":".tes"}`
    }
];


---

3. URL

> Tombol ini memungkinkan pengguna untuk membuka tautan URL secara langsung.
Maksimal 1 tombol URL dalam satu pesan.



const buttons = [
    {
        name: "cta_url",
        params: `{"display_text":"Google","url":"https://www.google.com","merchant_url":"https://www.google.com"}`
    }
];


---

4. Call

> Tombol ini memungkinkan pengguna untuk langsung melakukan panggilan telepon.



const buttons = [
    {
        name: "cta_call",
        params: `{"display_text":"Call","id":"6281234567890"}`
    }
];


---

5. Copy

> Tombol ini memungkinkan pengguna untuk menyalin teks.



const buttons = [
    {
        name: "cta_copy",
        params: `{"display_text":"Copy","id":"123456789","copy_code":"message"}`
    }
];


---

6. Kirim Lokasi (Pesan)

> Tombol ini memungkinkan pengguna untuk mengirim lokasi langsung dari pesan.



const buttons = [
    {
        name: "address_message",
        params: `{"display_text":"Send Location","id":"location1"}`
    }
];


---

7. Kirim Lokasi (Dari Pengguna)

> Tombol ini memungkinkan pengguna untuk membagikan lokasi mereka secara langsung.



const buttons = [
    {
        name: "send_location",
        params: `""`
    }
];


---

📌 Kirim Button + Gambar

> Kombinasi antara list button dan gambar dalam satu pesan.



const buttons = [
    {
        "name": "single_select",
        "buttonParamsJson": `{
            "title": "LIST MENU",
            "sections": [{
                "title": "Select Menu",
                "rows": [{
                    "title": "judulmenu",
                    "description": "deskripsimenu",
                    "id": "idmenu"
                }]
            }]
        }`
    }
];

const imageUrl = "https://example.com/image.jpg"; // Ganti dengan URL gambar

await danz.sendBtnListImage(
    m.chat, 
    "Teks di sini", 
    "Pilih menu di bawah:", 
    imageUrl, 
    buttons, 
    m, 
    [m.sender]
);


---

📌 Kirim Button Tanpa Gambar

> Mengirim button tanpa gambar dalam satu pesan.



const buttons = [
    {
        name: "cta_url",
        params: `{"display_text":"Google","url":"https://www.google.com","merchant_url":"https://www.google.com"}`
    },
    {
        name: "cta_reply",
        params: `{"display_text":"Quick Reply","id":"message"}`
    }
];

await danz.sendBtnList(
    m.chat, 
    "Teksnya", 
    "Bot", 
    buttons, 
    m
);


---

📌 Kirim File

> Bisa mengirim berbagai jenis file seperti gambar, video, audio, dokumen, stiker, dan GIF.




---

1. Kirim Gambar

await danz.sendImage(
    m.chat, 
    'https://example.com/image.jpg', 
    'Ini adalah gambar dari URL', 
    m
);


---

2. Kirim Video

await danz.sendVideo(
    m.chat, 
    'https://sample-videos.com/video123/mp4/720/big_buck_bunny_720p_1mb.mp4', 
    'Ini adalah video dari URL', 
    m
);


---

3. Kirim Audio (MP3)

await danz.sendAudio(
    m.chat, 
    'https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3', 
    m
);


---

4. Kirim Dokumen

await danz.sendDocument(
    m.chat, 
    'https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf', 
    'Contoh.pdf', 
    'Ini adalah file PDF dari URL', 
    m
);


---

5. Kirim Stiker

await danz.sendSticker(
    m.chat, 
    'https://example.com/sticker.webp', 
    m
);


---

6. Kirim GIF

await danz.sendGif(
    m.chat, 
    'https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif', 
    'Ini adalah GIF dari URL', 
    m
);


---

📌 Catatan Penting

✅ Maksimal Ukuran File:

Gambar, Audio, Sticker, GIF → 16 MB

Video → 64 MB

Dokumen → 100 MB


✅ Batasan Button:

Maksimal 3 tombol CTA dalam satu pesan.

Maksimal 1 list dengan 10 item.


✅ Format File yang Didukung:

Image → .jpg, .jpeg, .png, .gif

Video → .mp4, .mkv, .avi, .mov

Audio → .mp3, .wav, .ogg, .m4a

Dokumen → .pdf, .docx, .xlsx, .pptx, .txt, .zip

Sticker → .webp

GIF → .gif, .mp4



---

💡 Tips

Pakai Buffer untuk performa lebih cepat dan pengiriman ulang.

Pakai URL untuk file besar dan koneksi internet stabil.

Kombinasikan button dan file untuk pengalaman pengguna yang lebih interaktif.



---

🚀 Kode sudah diatur rapi dan siap untuk di-push ke GitHub! 😎🔥

---

✅ **Sudah bersih, lengkap, dan siap dipublish di GitHub!** 😎🔥

