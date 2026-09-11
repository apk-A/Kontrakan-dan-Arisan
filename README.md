<!DOCTYPE html>

<html lang="id">
<head>
  <meta charset="UTF-8">

<meta name="viewport"
     content="width=device-width, initial-scale=1.0">

  <title>Kontrakan & Arisan</title>

<meta name="description"
     content="Aplikasi Manajemen Kontrakan dan Arisan">

<meta name="robots"
     content="index, follow">

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html,
    body {
      width: 100%;
      height: 100%;
      overflow: hidden;
      font-family: Arial, Helvetica, sans-serif;
      background: #f5f8ff;
    }

    #appFrame {
      width: 100%;
      height: 100%;
      border: 0;
      display: block;
    }

    #loading {
      position: fixed;
      inset: 0;
      z-index: 9999;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 15px;
      background: #f5f8ff;
      color: #172033;
    }

    .spinner {
      width: 46px;
      height: 46px;
      border: 5px solid #dbeafe;
      border-top-color: #2563eb;
      border-radius: 50%;
      animation: spin 0.8s linear infinite;
    }

    .loading-text {
      font-size: 14px;
      font-weight: 600;
    }

    @keyframes spin {
      to {
        transform: rotate(360deg);
      }
    }

    #errorBox {
      position: fixed;
      inset: 0;
      display: none;
      align-items: center;
      justify-content: center;
      padding: 20px;
      background: #f5f8ff;
    }

    .error-card {
      width: 100%;
      max-width: 500px;
      background: #fff;
      border: 1px solid #e3eaf5;
      border-radius: 18px;
      padding: 25px;
      text-align: center;
      box-shadow: 0 15px 40px rgba(37,99,235,.10);
    }

    .error-card h2 {
      margin-bottom: 10px;
      color: #dc2626;
    }

    .error-card p {
      color: #64748b;
      line-height: 1.6;
      font-size: 14px;
      margin-bottom: 18px;
    }

    .btn {
      display: inline-block;
      padding: 11px 16px;
      border-radius: 11px;
      text-decoration: none;
      color: white;
      background: #2563eb;
      font-weight: 600;
      font-size: 13px;
    }
  </style>

</head>

<body>

  <div id="loading">
    <div class="spinner"></div>
    <div class="loading-text">
      Memuat aplikasi Kontrakan & Arisan...
    </div>
  </div>

  <iframe
    id="appFrame"
    title="Kontrakan & Arisan"
    allow="camera; microphone"
    allowfullscreen>
  </iframe>

  <div id="errorBox">
    <div class="error-card">
      <h2>Aplikasi Tidak Dapat Dibuka</h2>
      <p>
        Halaman Google Apps Script tidak dapat dimuat.
        Periksa URL Web App atau status deployment Apps Script Anda.
      </p>

```
  <a
    id="openApp"
    class="btn"
    href="#"
    target="_blank"
    rel="noopener">
    Buka Aplikasi Langsung
  </a>
</div>
```

  </div>

  <script>
    /*
     * ==========================================================
     * URL WEB APP GOOGLE APPS SCRIPT
     * ==========================================================
     *
     * GANTI URL DI BAWAH dengan URL deployment Web App Anda.
     *
     * Contoh:
     * https://script.google.com/macros/s/XXXXXXXXXXXX/exec
     *
     * Gunakan URL deployment yang berakhiran /exec
     */

    const APPS_SCRIPT_URL =
      "https://script.google.com/macros/s/AKfycbzf2P0erQwKB7R9AmmJpDJgI4otFEAEO5r7A0h2c6HASa2h1pR21sN4jc03BLJUwy1m/exec";


    const frame = document.getElementById("appFrame");
    const loading = document.getElementById("loading");
    const errorBox = document.getElementById("errorBox");
    const openApp = document.getElementById("openApp");


    /*
     * Memuat Apps Script
     */
    frame.src = APPS_SCRIPT_URL;


    /*
     * Saat iframe selesai dimuat
     */
    frame.addEventListener("load", function () {
      loading.style.display = "none";
      errorBox.style.display = "none";
    });


    /*
     * Fallback apabila terjadi masalah
     */
    window.setTimeout(function () {

      /*
       * Jangan langsung menampilkan error apabila
       * loading masih memungkinkan terjadi karena jaringan lambat.
       *
       * Waktu 15 detik dapat diubah.
       */

      if (loading.style.display !== "none") {

        loading.style.display = "none";
        errorBox.style.display = "flex";

        openApp.href = APPS_SCRIPT_URL;
      }

    }, 15000);


    /*
     * Menyesuaikan judul halaman
     */
    document.title = "Kontrakan & Arisan";
  </script>

</body>
</html>
