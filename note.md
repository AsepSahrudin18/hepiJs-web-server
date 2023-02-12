untuk  inisialisasi proyek gunakan perintah:

npm init --y

Lanjut, kita atur NPM runner pada package.json menjadi seperti ini:

"scripts": {
   "start": "node server.js"
},


## Membuat HTTP Server menggunakan hepi:

Untuk membuat HTTP server menggunakan Hapi, kita tidak lagi menggunakan core module http secara langsung. Namun, kita akan membuat server melalui modul pihak ketiga @hapi/hapi. Untuk menggunakan modul tersebut, kita perlu memasang terlebih dahulu melalui NPM dengan perintah.


npm install @hapi/hapi


Proses instalasi modul selesai! Kita lanjut ke penulisan kode pada berkas server.js.

Silakan hapus kode yang ada pada server.js, lalu ganti dengan kode dasar dalam pembuatan server menggunakan Hapi berikut ini:

const Hapi = require('@hapi/hapi');
 
const init = async () => {
    const server = Hapi.server({
        port: 5000,
        host: 'localhost',
    });
 
    await server.start();
    console.log(`Server berjalan pada ${server.info.uri}`);
};
 
init();
