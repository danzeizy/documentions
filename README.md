Berikut documentions WhatsApp by Danz Fyz! 😎🔥


---

# 🚀 WhatsApp Bot - List Button dan Pengiriman File

## **📌 List Button yang Tersedia**

---

### **1. Button List (Single Select)**
> Button ini digunakan untuk menampilkan list pilihan.  
> Maksimal **1 list** dengan **10 item** dalam satu pesan.  

```
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

```

## **2. Quick Reply**

> Tombol ini memungkinkan pengguna untuk membalas pesan dengan cepat.
Maksimal 3 quick reply dalam satu pesan.


```
case 'cmd':
			case 'menu':{
				let timestampe = speed();
				let latensie = speed() - timestampe;
				let a = db.data.users[m.sender];
				let me = m.sender;
				let teks = `┌──❖ Halo, Kak ${pushname}! 👋✨\n│ ✧ ${ucapanWaktu} yaa! 😊\n└────────────⳹\n\n${readmore}🌟 *𝐁𝐎𝐓 𝐈𝐍𝐅𝐎*\n⨳ *Speed:* ${latensie.toFixed(4)} ms\n⨳ *Runtime:* ${runtime(process.uptime())}\n⨳ *Bot:* ${botName}\n⨳ *Owner:* +${ownerNumber}\n⨳ *Mode:* ${haruka.public ? 'Public' : 'Self'}\n⨳ *Platform:* ${os.platform()}\n⨳ *Total User:* ${Object.keys(db.data.users).length}\n⨳ *Total Chat:* ${Object.keys(global.db.data.chats).length}\n\n🧍 *𝐔𝐒𝐄𝐑 𝐈𝐍𝐅𝐎*\n⨳ *Nama:* ${pushname}\n⨳ *Number:* +${me.split('@')[0]}\n⨳ *Limit:* ${a.limit}\n⨳ *Status:* ${isVip ? 'VIP User' : isPremium ? 'Premium User' : 'Free User'}\n⨳ *Serial:* ${a.serialNumber}\n\n🕒 *𝐓𝐈𝐌𝐄 𝐈𝐍𝐅𝐎*\n⨳ *Time:* ${time}\n⨳ *Date:* ${date}\n\n✨ *Silahkan pilih menu di bawah ini, Kak!* 🥰`;
				let msg = generateWAMessageFromContent(m.chat, {
					viewOnceMessage: {
						message: {
							"messageContextInfo": {
								"deviceListMetadata": {},
								"deviceListMetadataVersion": 2
							},
							interactiveMessage: proto.Message.InteractiveMessage.create({
								body: proto.Message.InteractiveMessage.Body.create({
									text: teks
								}),
								footer: proto.Message.InteractiveMessage.Footer.create({
									text: ownerName
								}),
								header: proto.Message.InteractiveMessage.Header.create({
									...(await prepareWAMessageMedia({ image: thumb }, { upload: haruka.waUploadToServer })), 
									title: '',
									subtitle: '',
									hasMediaAttachment: false
								}),
								nativeFlowMessage: proto.Message.InteractiveMessage.NativeFlowMessage.create({
									buttons: [
										{
											"name": "single_select",
											"buttonParamsJson": `{
												"title": "Click Here ⎙",
												"sections": [{
													"title": "Select Menu",
													"rows": [{
														"title": "📚 All Menu",
														"description": "Lihat semua menu seru di sini, kak! 🌟",
														"id": "${prefix}allmenu"
													},
													{
														"title": "🗝️ Owner's Secret Room",
														"description": "Psst... Rahasia nih! Cuma kakak spesial yang bisa masuk~ 🤫",
														"id": "${prefix}ownermenu"
													},
													{
														"title": "👥 Group Menu",
														"description": "Ayo intip menu khusus grup, seru-seruan bareng! 👥",
														"id": "${prefix}groupmenu"
													},
													{
														"title": "🔍 Search Menu",
														"description": "Cari apa aja di sini, Mora bantu nemuin kok~ 🔍",
														"id": "${prefix}searchmenu"
													},
													{
														"title": "📥 Download Menu",
														"description": "Unduh apa yang kakak butuhin, gampang kok! 📥",
														"id": "${prefix}downloadmenu"
													},
													{
														"title": "🛠️ Converter/Tools Menu",
														"description": "Bikin stiker, ubah audio, dan banyak alat seru lainnya di sini, Kak! 🎵✨",
														"id": "${prefix}convertmenu"
													},
													{
														"title": "🛒 Store Menu",
														"description": "Belanja-belanja lucu di sini aja, kak! 🛒",
														"id": "${prefix}storemenu"
													},
													{
														"title": "🦖 Pterodactyl Menu",
														"description": "Fitur panel Pterodactyl untuk mengelola server, menambah atau menghapus user, serta mengatur sumber daya server dengan mudah.",
														"id": "${prefix}panelmenu"
													},
													{
														"title": "🎮 Game Menu",
														"description": "Fitur Game untuk seru-seruan seperti tebak-tebakan dsb. 😋",
														"id": "${prefix}gamemenu"
													},
													{
														"title": "🎉 Fun Menu",
														"description": "Fitur Fun untuk seru-seruan, dicoba yuk! ✨",
														"id": "${prefix}funmenu"
													},
													{
														"title": "😋 Random Anime Menu",
														"description": "Menu yang berisi gambar Anime, cari gambar waifu kamu disini ya! 😍",
														"id": "${prefix}randomanimemenu"
													},
													{
														"title": "✨ Other Menu",
														"description": "Menu tambahan yang nggak kalah menarik, cek yuk! 💫",
														"id": "${prefix}othermenu"
													}]
												}]
											}`
										},
										{
											"name": "cta_url",
											"buttonParamsJson": `{
												"display_text": "My Handsome Owner 🐬",
												"url": "https://api.whatsapp.com/send?phone=${ownerNumber}",
												"merchant_url": "https://www.google.com"
											}`
										}
									],
								}),
								contextInfo: {
									mentionedJid: [m.sender], 
									forwardingScore: 999999,
									isForwarded: true,
									forwardedNewsletterMessageInfo: {
										newsletterJid: saluran,
										newsletterName: saluranName,
										serverMessageId: 143
									}
								}
							})
						}
					}
				}, { 
					quoted: m 
				})

				await haruka.relayMessage(
					msg.key.remoteJid, 
					msg.message, { 
						messageId: msg.key.id 
					}
				);
```

## **3. URL**

> Tombol ini memungkinkan pengguna untuk membuka tautan URL secara langsung.
Maksimal 1 tombol URL dalam satu pesan.


```
const buttons = [
    {
        name: "cta_url",
        params: `{"display_text":"Google","url":"https://www.google.com","merchant_url":"https://www.google.com"}`
    }
];
```

## **4. Call**

> Tombol ini memungkinkan pengguna untuk langsung melakukan panggilan telepon.


```
const buttons = [
    {
        name: "cta_call",
        params: `{"display_text":"Call","id":"6281234567890"}`
    }
];
```

## **5. Copy**

> Tombol ini memungkinkan pengguna untuk menyalin teks.

```
const buttons = [
    {
        name: "cta_copy",
        params: `{"display_text":"Copy","id":"123456789","copy_code":"message"}`
    }
];
```

## **6. Kirim Lokasi (Pesan)**

> Tombol ini memungkinkan pengguna untuk mengirim lokasi langsung dari pesan.

```
const buttons = [
    {
        name: "address_message",
        params: `{"display_text":"Send Location","id":"location1"}`
    }
];
```

## *7. Kirim Lokasi (Dari Pengguna)*

> Tombol ini memungkinkan pengguna untuk membagikan lokasi mereka secara langsung.

```
const buttons = [
    {
        name: "send_location",
        params: `""`
    }
];
```

## *📌 Kirim Button + Gambar*

> Kombinasi antara list button dan gambar dalam satu pesan.

```
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

await danz.sendBtnimg(m.chat, teks, danzres, buttons, m, [ m.sender,]);
```
Untuk code nya agak beda ya
```
 {
               "name": "cta_reply",
               "buttonParamsJson": "{\"display_text\":\"quick_reply\",\"id\":\"message\"}"
             }
```

## *📌 Kirim Button Tanpa Gambar*

> Mengirim button tanpa gambar dalam satu pesan.

```
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
                              "title": "Opsi 1",
                              "description": "Deskripsi Opsi 1",
                              "id": "id1"
                          }
                      ]
                  }
              ]
          }`
      }
    ];

await danz.sendBtn(
      m.chat, 
      "Teksnya", 
      buttons, 
      m
    );
```

## *📌 Kirim File*

> Bisa mengirim berbagai jenis file seperti gambar, video, audio, dokumen, stiker, dan GIF.


1. Kirim Gambar

```
await danz.sendImage(
    m.chat, 
    'https://example.com/image.jpg', 
    'Ini adalah gambar dari URL', 
    m
);
```

2. Kirim Video

```
await danz.sendVideo(
    m.chat, 
    'https://sample-videos.com/video123/mp4/720/big_buck_bunny_720p_1mb.mp4', 
    'Ini adalah video dari URL', 
    m
);
```

3. Kirim Audio (MP3)

```
await danz.sendAudio(
    m.chat, 
    'https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3', 
    m
);
```

4. Kirim Dokumen

```
await danz.sendDocument(
    m.chat, 
    'https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf', 
    'Contoh.pdf', 
    'Ini adalah file PDF dari URL', 
    m
);
```

5. Kirim Stiker

```
await danz.sendSticker(
    m.chat, 
    'https://example.com/sticker.webp', 
    m
);
```

6. Kirim GIF

```
await danz.sendGif(
    m.chat, 
    'https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif', 
    'Ini adalah GIF dari URL', 
    m
);
```

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
