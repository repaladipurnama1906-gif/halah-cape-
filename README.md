<!doctype html>
<html lang="id">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game Android - MOBA Filter</title>
    
    <style>
      body {
        margin: 0;
        font-family: Arial, sans-serif;
        background: #f5f5f5;
        color: #333;
      }

      main {
        max-width: 900px;
        margin: 30px auto;
        padding: 20px;
      }

      .game-populer {
        background: white;
        padding: 20px;
        border-radius: 12px;
        box-shadow: 0 4px 10px rgba(0,0,0,.1);
      }

      h1 {
        color: #0d6efd;
        text-transform: capitalize;
      }

      h2 {
        margin-top: 30px;
      }

      h3 {
        color: #198754;
        margin-bottom: 5px;
      }

      li {
        margin-bottom: 10px;
      }

      /* --- STYLE UNTUK TOMBOL FILTER --- */
      .filter-container {
        margin: 20px 0;
        display: flex;
        gap: 10px;
        flex-wrap: wrap;
      }

      .btn-filter {
        background-color: #e2e8f0;
        color: #4a5568;
        border: none;
        padding: 8px 16px;
        font-size: 14px;
        font-weight: bold;
        border-radius: 20px;
        cursor: pointer;
        transition: all 0.3s ease;
      }

      .btn-filter:hover {
        background-color: #cbd5e1;
      }

      .btn-filter.active {
        background-color: #0d6efd;
        color: white;
      }

      /* --- ANIMASI SEMBUNYIKAN GAME --- */
      .game-item {
        transition: all 0.4s ease;
        overflow: hidden;
      }

      .game-item.hide {
        display: none;
      }
    </style>
  </head>
  <body>
    <main>
      <section class="game-populer">
        <h1>game moba</h1>
        <p>game moba merupakan jenis game yang <strong>sangat populer</strong> hingga hampir semua orang mengetahuinya.</p>
     
        <h2>Penggunaan HP (Mobile MOBA)</h2>

        <div class="filter-container">
          <button class="btn-filter active" data-filter="all">Semua</button>
          <button class="btn-filter" data-filter="pemula">Cocok untuk Pemula</button>
          <button class="btn-filter" data-filter="grafis">Grafis Tinggi</button>
          <button class="btn-filter" data-filter="taktis">Taktis & Kompleks</button>
        </div>
        
        <div class="game-item" data-category="pemula">
          <h3>Mobile Legends: Bang Bang (MLBB)</h3>
          <ul>
            <li>
              <strong>Kelebihan:</strong> Game MOBA paling populer di Indonesia saat ini. Mencari pertandingan sangat cepat, durasi bermain singkat, dan komunitasnya sangat besar.
            </li>
            <li>
              <strong>Gameplay:</strong> Kontrolnya ramah pengguna untuk pemula dengan pilihan hero yang sangat banyak.
            </li>
          </ul> 
        </div>

        <div class="game-item" data-category="grafis">
          <h3>Honor of Kings (HoK)</h3>
          <ul>
            <li>
              <strong>Kelebihan:</strong> Mengangkat tema mitologi Tiongkok. Grafis dan kualitas visual heronya sangat memanjakan mata dan rilis secara global.
            </li>
            <li>
              <strong>Gameplay:</strong> Ritme permainannya cepat, penuh aksi, dan ramah bagi pemain baru.
            </li>
          </ul>
        </div>

        <div class="game-item" data-category="taktis">
          <h3>League of Legends: Wild Rift</h3>
          <ul>
            <li>
              <strong>Kelebihan:</strong> Versi mobile resmi dari game legendaris PC. Memiliki grafis yang sangat halus dan mekanisme yang lebih adil.
            </li>
            <li>
              <strong>Gameplay:</strong> Sedikit lebih kompleks dibanding MLBB karena membutuhkan penempatan ward (pendeteksi musuh) secara manual untuk strategi yang lebih mendalam.
            </li>
          </ul>
        </div>

      </section>
    </main>

    <script>
      // 1. Ambil semua elemen tombol dan item game
      const filterButtons = document.querySelectorAll('.btn-filter');
      const gameItems = document.querySelectorAll('.game-item');

      // 2. Berikan fungsi klik pada setiap tombol
      filterButtons.forEach(button => {
        button.addEventListener('click', () => {
          
          // Ubah status tombol yang aktif
          document.querySelector('.btn-filter.active').classList.remove('active');
          button.classList.add('active');

          // Ambil target filter dari atribut data-filter
          const filterValue = button.getAttribute('data-filter');

          // 3. Logika menyaring game
          gameItems.forEach(item => {
            const itemCategory = item.getAttribute('data-category');

            if (filterValue === 'all' || filterValue === itemCategory) {
              item.classList.remove('hide'); // Tampilkan game
            } else {
              item.classList.add('hide');    // Sembunyikan game
            }
          });

        });
      });
    </script>
  </body>
</html>