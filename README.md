!DOCTYPE html>
<html lang="az">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Blood Guardians</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background: #080808;
      color: #f4f4f4;
      font-family: Arial, Helvetica, sans-serif;
      line-height: 1.7;
    }

    header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 10;
      background: rgba(0, 0, 0, 0.88);
      border-bottom: 1px solid #333;
      backdrop-filter: blur(10px);
    }

    nav {
      max-width: 1150px;
      margin: auto;
      padding: 16px 24px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      color: white;
      text-decoration: none;
      font-size: 21px;
      font-weight: bold;
      letter-spacing: 2px;
    }

    .logo span {
      color: #789cff;
    }

    nav ul {
      display: flex;
      gap: 22px;
      list-style: none;
    }

    nav a {
      color: #ddd;
      text-decoration: none;
      font-size: 14px;
      transition: 0.3s;
    }

    nav a:hover {
      color: #789cff;
    }

    .hero {
      min-height: 100vh;
      padding: 120px 24px 70px;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      overflow: hidden;
      background:
        linear-gradient(90deg, rgba(0,0,0,.95), rgba(0,0,0,.52), rgba(0,0,0,.9)),
        url("5197.png") center / cover;
    }

    .hero-content {
      width: 100%;
      max-width: 1150px;
      display: grid;
      grid-template-columns: 1fr 390px;
      gap: 55px;
      align-items: center;
    }

    .hero-text small {
      color: #9aaeff;
      letter-spacing: 4px;
      font-weight: bold;
    }

    .hero h1 {
      font-size: clamp(45px, 8vw, 96px);
      line-height: .95;
      margin: 18px 0;
      letter-spacing: -3px;
      text-transform: uppercase;
    }

    .hero h1 span {
      color: #789cff;
      display: block;
    }

    .hero p {
      max-width: 590px;
      color: #d0d0d0;
      font-size: 17px;
      margin-bottom: 28px;
    }

    .buttons {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
    }

    .button {
      display: inline-block;
      padding: 12px 22px;
      border: 1px solid white;
      text-decoration: none;
      color: white;
      font-weight: bold;
      transition: .3s;
    }

    .button.primary {
      background: white;
      color: black;
    }

    .button:hover {
      background: #789cff;
      border-color: #789cff;
      color: white;
    }

    .cover {
      border: 1px solid #555;
      box-shadow: 0 0 50px rgba(90, 120, 255, .28);
      transform: rotate(2deg);
      transition: .4s;
    }

    .cover:hover {
      transform: rotate(0deg) scale(1.03);
    }

    .cover img {
      width: 100%;
      display: block;
    }

    section {
      max-width: 1150px;
      margin: auto;
      padding: 90px 24px;
    }

    .section-title {
      margin-bottom: 35px;
    }

    .section-title small {
      color: #789cff;
      letter-spacing: 3px;
      text-transform: uppercase;
    }

    .section-title h2 {
      font-size: clamp(30px, 5vw, 52px);
      margin-top: 8px;
    }

    .about {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 45px;
      align-items: start;
    }

    .about p {
      color: #cfcfcf;
      margin-bottom: 15px;
    }

    .info-box {
      border: 1px solid #333;
      padding: 25px;
      background: #101010;
    }

    .info-box div {
      display: flex;
      justify-content: space-between;
      gap: 20px;
      padding: 12px 0;
      border-bottom: 1px solid #292929;
    }

    .info-box div:last-child {
      border-bottom: none;
    }

    .info-box span:first-child {
      color: #888;
    }

    .chapters {
      display: grid;
      gap: 20px;
    }

    details {
      background: #101010;
      border: 1px solid #333;
      overflow: hidden;
    }

    summary {
      cursor: pointer;
      list-style: none;
      padding: 23px 25px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      font-size: 20px;
      font-weight: bold;
      transition: .3s;
    }

    summary::-webkit-details-marker {
      display: none;
    }

    summary::after {
      content: "+";
      color: #789cff;
      font-size: 28px;
      font-weight: normal;
    }

    details[open] summary::after {
      content: "−";
    }

    summary:hover {
      background: #181818;
    }

    .chapter-content {
      padding: 8px 25px 30px;
      border-top: 1px solid #333;
    }

    .chapter-intro {
      color: #aaa;
      font-style: italic;
      margin: 20px 0 28px;
    }

    .scene {
      margin: 28px 0;
      padding-left: 18px;
      border-left: 2px solid #789cff;
    }

    .scene h3 {
      color: white;
      margin-bottom: 12px;
      font-size: 19px;
    }

    .panel {
      background: #171717;
      padding: 12px 15px;
      margin: 8px 0;
      border-radius: 2px;
      color: #d6d6d6;
    }

    .panel strong {
      color: #789cff;
    }

    .quote {
      margin: 12px 0;
      padding: 12px 17px;
      border-left: 3px solid #789cff;
      color: #fff;
      background: #0b0b0b;
      font-style: italic;
    }

    footer {
      border-top: 1px solid #282828;
      text-align: center;
      padding: 35px 20px;
      color: #777;
      font-size: 14px;
    }

    footer strong {
      color: #789cff;
    }

    @media (max-width: 800px) {
      nav {
        padding: 14px 17px;
      }

      nav ul {
        gap: 11px;
      }

      nav a {
        font-size: 12px;
      }

      .hero-content,
      .about {
        grid-template-columns: 1fr;
      }

      .hero {
        padding-top: 125px;
      }

      .hero-text {
        text-align: center;
      }

      .hero p {
        margin-left: auto;
        margin-right: auto;
      }

      .buttons {
        justify-content: center;
      }

      .cover {
        max-width: 330px;
        margin: 10px auto 0;
      }

      section {
        padding: 65px 17px;
      }

      summary {
        padding: 18px;
        font-size: 17px;
      }

      .chapter-content {
        padding: 5px 18px 24px;
      }
    }
  </style>
</head>

<body>

  <header>
    <nav>
      <a href="#ana-sehife" class="logo">
        BLOOD <span>GUARDIANS</span>
      </a>

      <ul>
        <li><a href="#haqqinda">Haqqında</a></li>
        <li><a href="#fesiller">Fəsillər</a></li>
      </ul>
    </nav>
  </header>

  <main id="ana-sehife">

    <section class="hero">
      <div class="hero-content">
        <div class="hero-text">
          <small>ORİJİNAL MANQA SSENARİSİ</small>
          <h1>Blood <span>Guardians</span></h1>

          <p>
            Qarlı gecədə başlayan faciə, vampirlərə qarşı mübarizə
            və içində gizlənən sirli gücü kəşf edən Yoro-nun hekayəsi.
          </p>

          <div class="buttons">
            <a href="#fesiller" class="button primary">Oxumağa başla</a>
            <a href="#haqqinda" class="button">Haqqında</a>
          </div>
        </div>

        <div class="cover">
          <div style="text-align:center">
  <img id="coverImage"
       alt="Blood Guardians üz qabığı"
       style="max-width:100%;max-height:550px;display:block;margin:20px auto">

  <label style="display:inline-block;background:white;color:black;padding:12px 20px;cursor:pointer;font-weight:bold">
    Üz qabığını seç
    <input type="file"
           accept="image/*"
           onchange="loadCover(event)"
           style="display:none">
  </label>
</div>

<script>
function loadCover(event) {
  const file = event.target.files[0];

  if (file) {
    document.getElementById("coverImage").src =
      URL.createObjectURL(file);
  }
}
</script>
        </div>
      </div>
    </section>

    <section id="haqqinda">
      <div class="section-title">
        <small>Hekayə haqqında</small>
        <h2>Qanla yazılmış tale</h2>
      </div>

      <div class="about">
        <div>
          <p>
            Yoro ailəsi ilə birlikdə dağ kənarındakı kənddə yaşayan
            on altı yaşlı bir gəncdir. Bir qış gecəsi evə qayıdarkən
            ailəsini vampirin hücumuna məruz qalmış vəziyyətdə tapır.
          </p>

          <p>
            Atasının son əmri Yoro-nun həyatını dəyişir:
            qaçmaq, Geri-ni qorumaq və yaşamaq.
          </p>

          <p>
            Vampir Ovçuları Birliyinə qoşulan Yoro məşq etməyə başlayır.
            Lakin heç bir xüsusi gücə sahib olmadığı düşünülən bu gəncin
            boynundakı əmanət əslində böyük bir sirr daşıyır.
          </p>
        </div>

        <div class="info-box">
          <div>
            <span>Janr</span>
            <strong>Fantastika / Dram</strong>
          </div>
          <div>
            <span>Mövzu</span>
            <strong>Vampirlər və ovçular</strong>
          </div>
          <div>
            <span>Baş qəhrəman</span>
            <strong>Yoro</strong>
          </div>
          <div>
            <span>Status</span>
            <strong>Davam edir</strong>
          </div>
        </div>
      </div>
    </section>

    <section id="fesiller">
      <div class="section-title">
        <small>Oxu bölməsi</small>
        <h2>Fəsillər</h2>
      </div>

      <div class="chapters">

        <!-- Fəsil 1 -->
        <toggle>
          Fəsil 1: Qarlı Gecə

          <div class="chapter-content">
            <p class="chapter-intro">
              Zaman: 2016-cı il, qış |
              Məkan: Dağ kənarındakı kənd evi
            </p>

            <div class="scene">
              <h3>Səhnə 1 — Evə dönüş</h3>

              <div class="panel">
                <strong>Panel 1:</strong>
                Qarlı dağ yolu. İki fiqur uzaqdan gəlir.
                Atanın arxasında Yoro odun arabasını itələyir.
              </div>

              <div class="panel">
                <strong>Panel 2:</strong>
                Yoro yorğun, amma sakit görünür.
              </div>

              <div class="quote">
                Yoro: “Bu qədər odun satdıq... bu dəfə bəlkə ana üçün də bir şey alarıq.”
              </div>

              <div class="panel">
                <strong>Panel 3:</strong>
                Ev görünür. Qapı yarı açıqdır. Qarın üzərində qəribə ayaq izləri var.
              </div>

              <div class="quote">
                Ata: “...Yoro.”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 2 — Faciə</h3>

              <div class="quote">
                Ata: “Qaç. Burdan tez ol. Geri baxma.”
              </div>

              <div class="panel">
                Yoro çaşqın halda atasına baxır. Ata isə evə doğru qaçır.
                Evin içində yıxılmış mebel, qan izləri və ailənin cansız
                bədənləri görünür.
              </div>

              <div class="panel">
                Küncdə vampir dayanıb. Əlində on yaşlı Geri var.
              </div>

              <div class="quote">
                Ata: “Onu burax!!”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 3 — Əmanət</h3>

              <div class="panel">
                Ata qan içində çölə çıxır. Əlində Geri var.
              </div>

              <div class="panel">
                Ata Geri-ni Yoro-nun qucağına verir və onun paltarının içinə
                bir boyun bağı qoyur.
              </div>

              <div class="quote">
                Ata: “Al... onu götür... və qaç.”
              </div>

              <div class="quote">
                Yoro: “Ata... ana? Qardaşlar...?”
              </div>

              <div class="quote">
                Ata: “İndi danışma vaxtı deyil. Qaç!”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 4 — Təqib</h3>

              <div class="panel">
                Yoro Geri-ni qucaqlayıb qarlı yolda qaçır.
                Arxadan atasının qışqırığı gəlir, sonra sükut yaranır.
              </div>

              <div class="quote">
                Vampir: “Hara gedirsiniz belə...? Mən hələ doymamışam.”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 5 — Martis</h3>

              <div class="panel">
                Kəskin metal səsi eşidilir. Martis adlı vampir ovçusu
                vampirin boynuna xüsusi bıçaq saplayır.
              </div>

              <div class="panel">
                Vampir qışqıraraq dağılır. Martis Yoro və Geri-yə baxır.
              </div>

              <div class="quote">
                Martis: “...Hələ də sağsınız. Yaxşı.”
              </div>

              <div class="quote">
                Martis: “Mənim adım Martis. Vampir ovçuları
                birliyindənəm. Sizi təhlükəsiz yerə aparacağam.”
              </div>

              <div class="panel">
                Yoro qarın altında atasını, Geri-ni və Martis-i düşünür.
              </div>

              <div class="quote">
                Yoro: “...Ata... mən nə etməliyəm?”
              </div>
            </div>

            <p class="chapter-intro">Fəsil 1 sonu.</p>
          </div>
        </toggle>

        <!-- Fəsil 2 -->
        <toggle>
          Fəsil 2: Birlik

          <div class="chapter-content">
            <p class="chapter-intro">
              Hadisələrdən bir neçə gün sonra |
              Məkan: Vampir Ovçuları Birliyinin binası
            </p>

            <div class="scene">
              <h3>Səhnə 1 — Binaya gəliş</h3>

              <div class="panel">
                Böyük, qədim daş bina. Qar yağmağa davam edir.
                Martis öndə gedir, Yoro isə Geri-ni qucağında daşıyır.
              </div>

              <div class="panel">
                Qapıda 21 yaşlı Kimi dayanır. Uzun saçlı, sakit baxışlı
                və ağ xalat geyinib.
              </div>

              <div class="quote">
                Kimi: “Martis... yenə uşaq gətirmisən?”
              </div>

              <div class="quote">
                Martis: “Bu dəfə fərqlidirlər. Onları sənə əmanət edirəm.”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 2 — Xəstəxana</h3>

              <div class="panel">
                Kimi Yoro və Geri-ni xəstəxana otağına aparır.
                Geri müayinə edilir, Yoro isə kənarda dayanır.
              </div>

              <div class="quote">
                Yoro: “Mən... heç nə edə bilmədim.”
              </div>

              <div class="panel">
                Günlər keçir. Yoro pəncərədən bayıra baxır,
                Geri isə çarpayıda yatır.
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 3 — Yoro çölə çıxır</h3>

              <div class="panel">
                Bir səhər Yoro xəstəxana otağından çıxır.
                Uzun dəhlizlərdən keçərkən uzaqdan qılınc səsləri eşidir.
              </div>

              <div class="panel">
                Təlim sahəsində bir neçə gənc şagird döyüşür.
                Martis onlara əmr verir.
              </div>

              <div class="quote">
                Martis: “Yenidən! Daha sürətli!”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 4 — Təlimi izləmək</h3>

              <div class="panel">
                Bir şagird qılıncını alova bürüyür.
                Digəri yerdən daş divar qaldırır.
                Başqa biri külək yaradır.
              </div>

              <div class="quote">
                Martis: “Xəstəxanadan qaçmısan?”
              </div>

              <div class="quote">
                Yoro: “...Daha dözə bilmədim.”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 5 — Qərar</h3>

              <div class="quote">
                Yoro: “Mən də sizinlə döyüşməyi öyrənmək istəyirəm.
                Vampirləri... onların hamısını məhv etmək istəyirəm.”
              </div>

              <div class="quote">
                Martis: “Hə.”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 6 — Həftələr sonra</h3>

              <div class="panel">
                Qar əriyir, günlər keçir. Yoro məşq edir.
                Qılıncını silkələsə də, heç bir xüsusi güc göstərə bilmir.
              </div>

              <div class="panel">
                Digər şagirdlər onun haqqında pıçıldaşırlar.
                Martis isə uzaqdan Yoro-nu diqqətlə izləyir.
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 7 — Yeni tanışlıqlar</h3>

              <div class="panel">
                Martis Yoro-nu iki şagirdin yanına aparır:
                Tan və Barou.
              </div>

              <div class="quote">
                Tan: “Salam! Mən Tanam! Qılınc və alov istifadə edirəm!”
              </div>

              <div class="quote">
                Barou: “...Barou.”
              </div>

              <div class="panel">
                Kimi onları uzaqdan izləyir.
              </div>

              <div class="quote">
                Kimi: “Ümid edirəm... bu uşaq özünü itirməz.”
              </div>
            </div>

            <p class="chapter-intro">Fəsil 2 sonu.</p>
          </div>
        </toggle>

        <!-- Fəsil 3 -->
        <toggle>
          Fəsil 3: İlk Missiya və Oyanış

          <div class="chapter-content">
            <p class="chapter-intro">
              Zaman: 3 ay sonra |
              Məkan: Vampir Ovçuları Birliyinin ətrafı və meşə
            </p>

            <div class="scene">
              <h3>Səhnə 1 — Üç ay sonra</h3>

              <div class="panel">
                Bahar gəlib. Qar əriyib. Yoro, Tan və Barou
                təlim sahəsində məşq edirlər.
              </div>

              <div class="quote">
                Martis: “5 sadə qan sorucu. Meşəlikdə.
                Bu dəfə sən də gələcəksən, Yoro.”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 2 — Missiya öncəsi</h3>

              <div class="panel">
                Martis, Yoro, Tan və Barou meşənin kənarında gizləniblər.
                İrəlidə beş qan sorucu görünür.
              </div>

              <div class="quote">
                Martis: “Yoro... özünü hazır hiss edirsən?
                Bu sənin üçün təhlükəli ola bilər.”
              </div>

              <div class="quote">
                Yoro: “Mən aylardır hazıram.”
              </div>

              <div class="quote">
                Martis: “Çıxın.”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 3 — Döyüş</h3>

              <div class="panel">
                Barou və Tan dərhal hücuma keçirlər.
                Barou bədənini bərkidir, Tan isə qılıncını alova bürüyür.
              </div>

              <div class="panel">
                Yoro isə yerində donub qalır.
                Bədəni ona tabe olmur.
              </div>

              <div class="quote">
                Barou: “Çəkil!”
              </div>

              <div class="panel">
                Tan və Barou dörd qan sorucunu məhv edirlər.
              </div>

              <div class="quote">
                Tan: “Axı... bayaq burada 5 dənə var idi...”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 4 — Təhlükə</h3>

              <div class="panel">
                Beşinci qan sorucu Yoro-nun arxasından çıxır.
                Martis son anda yetişərək onun başını kəsir.
              </div>

              <div class="quote">
                Martis: “Yoro. Diqqətli olmalısan.”
              </div>

              <div class="quote">
                Yoro: “...Yaxşı.”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 5 — Növbəti gün</h3>

              <div class="panel">
                Yoro həyətə çıxıb təkbaşına məşq edir.
                Dünənki hadisə gözünün qabağından getmir.
              </div>

              <div class="quote">
                Yoro: “Aaaaaaa!”
              </div>

              <div class="quote">
                Tan: “Yoro, yaxşısan? İstəyirsən bir yerdə məşq edək?”
              </div>

              <div class="quote">
                Barou: “Hə... istəsən...”
              </div>

              <div class="quote">
                Yoro: “Yox, uşaqlar. Sağ olun.
                Amma bir az tək qalmalıyam.”
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 6 — Çay kənarı</h3>

              <div class="panel">
                Yoro meşənin dərinliyində çayın kənarında oturur.
                Əlində atasının Geri-yə verdiyi boyun bağı var.
              </div>

              <div class="quote">
                Yoro: “Ata... bu heç bir işə yaramayan boyun bağını
                niyə Geri-nin paltarına qoydun?”
              </div>

              <div class="quote">
                Yoro: “Niyə mənə vermək istədin?
                Məqsədin nə idi?”
              </div>

              <div class="panel">
                Arxadan budaq səsi gəlir. Yoro dərhal ayağa qalxır
                və qılıncına yapışır.
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 7 — İki qan sorucu</h3>

              <div class="panel">
                Kolların arasından iki qan sorucu çıxır.
                Onların gözləri aclıqdan parıldayır.
              </div>

              <div class="quote">
                Qan sorucu: “Ey balaca... deyəsən azmısan.
                Biz də çox acmışıq.”
              </div>

              <div class="panel">
                Yoro qorxu içində geri çəkilir.
                Keçmişdəki faciə onun gözləri önündə canlanır:
                ata, ana, qardaşları, qan və qar.
              </div>

              <div class="panel">
                Birdən boyun bağından zəif ağ işıq sızmağa başlayır.
                Yoro-nun gözləri də ağarmağa başlayır.
              </div>

              <div class="panel">
                Güclü ağ işıq partlayışı bütün meşəni işıqlandırır.
                İki qan sorucu qışqıraraq geriyə atılır.
              </div>
            </div>

            <div class="scene">
              <h3>Səhnə 8 — Nəticə</h3>

              <div class="panel">
                Martis, Tan və Barou işığı görüb hadisə yerinə qaçırlar.
              </div>

              <div class="panel">
                İki qan sorucu yerdə toza çevrilir.
                Ortada isə Yoro dayanıb.
              </div>

              <div class="panel">
                Yoro-nun gözlərindəki ağ işıq sönür.
                O, əlində hələ də zəif parıldayan boyun bağı ilə yerə yıxılır.
              </div>

              <div class="panel">
                Martis, Tan və Barou şok içində Yoro-ya baxırlar.
              </div>
            </div>

            <p class="chapter-intro">Fəsil 3 sonu.</p>
          </div>
        </toggle>

      </div>
    </section>

  </main>
