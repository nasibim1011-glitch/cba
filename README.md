 (cd "$(git rev-parse --show-toplevel)" && git apply --3way <<'EOF' 
diff --git a/README.md b/README.md
new file mode 100644
index 0000000000000000000000000000000000000000..e10be02be3c809f579c79feb1d7ab9c03d9dab2e
--- /dev/null
+++ b/README.md
@@ -0,0 +1,167 @@
+# open-notebook
+
+Bu depo, **`lfnovo/open-notebook`** projesini yerel ortama indirmek, çalıştırmak ve geliştirme akışını başlatmak için hazırlanmış Türkçe bir rehber içerir.
+
+> Kaynak depo: https://github.com/lfnovo/open-notebook
+
+---
+
+## 1) İndirme (Clone) Rehberi
+
+### Gereksinimler
+- Git (önerilen: 2.30+)
+- İnternet erişimi
+- Komut satırı (Terminal, PowerShell, VS Code Terminal)
+
+### Depoyu klonlama
+
+```bash
+git clone https://github.com/lfnovo/open-notebook.git
+cd open-notebook
+```
+
+### Belirli bir branch ile çalışma
+
+```bash
+git branch -a
+git checkout <branch-adi>
+```
+
+### Depoyu güncelleme
+
+```bash
+git pull origin <branch-adi>
+```
+
+---
+
+## 2) Çalıştırma Rehberi (Hızlı Başlangıç)
+
+> Projenin kullandığı teknolojiye göre aşağıdaki uygun başlığı seçin.
+
+### A) Node.js tabanlıysa
+
+```bash
+# bağımlılıkları kur
+npm install
+
+# geliştirme sunucusu
+npm run dev
+
+# üretim build
+npm run build
+npm start
+```
+
+Alternatif paket yöneticileri:
+
+```bash
+yarn
+yarn dev
+```
+
+```bash
+pnpm install
+pnpm dev
+```
+
+### B) Python tabanlıysa
+
+```bash
+# sanal ortam oluştur
+python -m venv .venv
+
+# aktif et (Linux/macOS)
+source .venv/bin/activate
+
+# aktif et (Windows PowerShell)
+# .venv\Scripts\Activate.ps1
+
+# bağımlılıklar
+pip install -r requirements.txt
+
+# çalıştırma (projenin giriş dosyasına göre)
+python app.py
+# veya
+python main.py
+```
+
+### C) Docker tabanlıysa
+
+```bash
+docker compose up --build
+```
+
+Arka planda çalıştırma:
+
+```bash
+docker compose up -d --build
+```
+
+---
+
+## 3) Projeyi İlk Açtığınızda Kontrol Edilecek Dosyalar
+
+Aşağıdaki dosyalar projenin nasıl çalıştırılacağını kesinleştirir:
+
+- `package.json` → Node.js komutları (`scripts` alanı)
+- `requirements.txt` / `pyproject.toml` → Python bağımlılıkları
+- `Dockerfile` / `docker-compose.yml` → Container tabanlı çalıştırma
+- `.env.example` → Ortam değişkenleri şablonu
+
+Örnek `.env` hazırlığı:
+
+```bash
+cp .env.example .env
+```
+
+---
+
+## 4) Geliştirme Akışı (Önerilen)
+
+```bash
+# yeni branch
+ git checkout -b docs/readme-kurulum-rehberi
+
+# değişiklikleri ekle
+ git add .
+
+# commit
+ git commit -m "docs: readme çalışma ve indirme rehberi eklendi"
+
+# uzak depoya gönder
+ git push origin docs/readme-kurulum-rehberi
+```
+
+---
+
+## 5) Sık Karşılaşılan Sorunlar
+
+### Git clone hatası
+- Ağ/proxy kısıtı olabilir.
+- HTTPS yerine SSH erişimi deneyin.
+
+### Bağımlılık kurulumu başarısız
+- Sürüm uyumsuzluğu olabilir (Node/Python).
+- Projenin beklediği sürümü kontrol edin (`.nvmrc`, `pyproject.toml`, docs).
+
+### Port çakışması
+- Uygulamanın kullandığı portu değiştirin (`.env` veya çalıştırma parametreleri).
+
+---
+
+## 6) Katkı Notu
+
+Katkı yapmadan önce mümkünse:
+- lint/test komutlarını çalıştırın,
+- küçük ve odaklı commitler atın,
+- pull request açıklamasında neyi neden değiştirdiğinizi belirtin.
+
+---
+
+## 7) Lisans
+
+Lisans bilgisi için kaynak depodaki lisans dosyasını kontrol edin:
+
+- https://github.com/lfnovo/open-notebook
+
 
EOF
)
