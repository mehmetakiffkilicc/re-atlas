# 🌍 RE-Atlas (EcoSentry) — Yenilenebilir Enerji Karar Destek Sistemi ⚡

[![Presentation](https://img.shields.io/badge/Google_Slides-Sunum-yellow?style=for-the-badge&logo=google-slides)](https://docs.google.com/presentation/d/1rX-tVf05HWTeZvsu54VjDCewtqR7RTpB/edit?usp=sharing&ouid=105394792343086173592&rtpof=true&sd=true)
![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![Leaflet](https://img.shields.io/badge/Leaflet-199900?style=for-the-badge&logo=Leaflet&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)

**RE-Atlas (EcoSentry)**, Türkiye genelinde güneş, rüzgar ve hibrit enerji yatırımları için veri odaklı analiz ve karar destek sağlayan kapsamlı bir web uygulamasıdır. Yüksek çözünürlüklü meteorolojik ve coğrafi verileri işleyerek, yatırımcılara anlık kapasite raporları ve projeksiyonlar sunar.

## 🚀 Proje Hakkında

Bu platform, yatırımcıların ve enerji uzmanlarının Türkiye'nin farklı bölgelerindeki enerji potansiyelini 1km çözünürlüğünde analiz etmelerine olanak tanır. Uygulama, gerçek zamanlı meteorolojik veriler, arazi kullanım bilgileri ve trafo merkezi yakınlığı gibi kritik faktörleri bir araya getirerek yatırım uygunluk skorları üretir.

## ✨ Temel Özellikler

*   **🗺️ Dinamik Alan ve Grid Analizi:** Harita üzerinde spesifik alanların analizini yapabilme. Sistem, seçilen alanı akıllı gridlere bölerek mikro-lokasyon bazlı hesaplamalar gerçekleştirir.
*   **🔥 Yüksek Performanslı Isı Haritaları:** Güneş (GHI) ve rüzgar enerjisi potansiyelini görselleştiren, Numpy ve Pillow ile işlenmiş yüksek çözünürlüklü statik katmanlar.
*   **📍 Noktasal Hassasiyet:** Tek bir koordinat seçimiyle o noktanın enerji potansiyelini, en yakın trafo merkezini ve arazi durumunu anında hesaplama.
*   **📈 Üretim Tahminleme (Forecasting):** Seçilen lokasyonlar için 48 saatlik ve 7 günlük ileriye dönük kapasite tahminleri.
*   **📊 Gelişmiş Dashboard:** Recharts ile görselleştirilmiş çift eksenli grafikler, dinamik kapasite barları ve yatırım yapılabilirlik rozetleri.
*   **🎥 Sinematik UI/UX:** Fokus modu, akıllı FlyTo efektleri ve Türkiye sınırlarına optimize edilmiş (maxBounds) akıcı kullanıcı deneyimi.

## 🛠️ Teknoloji Yığını

### Frontend
- **Framework:** React + Vite + TypeScript
- **Harita:** Leaflet & React-Leaflet & Turf.js
- **Animasyon & Stil:** Framer Motion + Tailwind CSS
- **State Management:** Zustand
- **Grafikler:** Recharts

### Backend & Veri İşleme
- **Framework:** FastAPI (Python)
- **Veri İşleme:** NumPy, Pandas, Rasterio, Pillow
- **API:** Open-Meteo Entegrasyonu
- **Coğrafi Veri:** GeoJSON ve GeoTIFF tabanlı yüksek performanslı veri servisleri

## ⚙️ Kurulum ve Çalıştırma

### Gereksinimler
- Node.js (v18+)
- Python (3.9+)

### Hızlı Başlangıç

Proje kök dizininde bulunan yardımcı scriptleri (Windows için) kullanabilirsiniz:

1.  **Bağımlılıkların Kurulumu:**
    ```bash
    # Backend
    cd backend
    pip install -r requirements.txt

    # Frontend
    cd ../frontend
    npm install
    ```

2.  **Uygulamayı Başlatma:**
    Kök dizindeki `start.bat` dosyasını çalıştırın veya manuel başlatın:
    - **Backend:** `cd backend && python -m uvicorn app.main:app --reload`
    - **Frontend:** `cd frontend && npm run dev`

## 📁 Proje Yapısı

```text
GreenGrid/
├── backend/            # FastAPI servisleri ve skorlama motoru
│   ├── app/            # Uygulama mantığı (routerlar, servisler, modeller)
│   └── data/           # Coğrafi veri dosyaları (GeoJSON, Grid data)
├── frontend/           # Vite + React kullanıcı arayüzü
│   ├── src/            # Bileşenler, hooklar ve state yönetimi
│   └── public/         # Statik varlıklar
├── data-pipeline/      # Veri çekme ve işleme betikleri
└── contracts/          # Paylaşılan veri şemaları (Pydantic modelleri)
```

## 📸 Görseller

| Güneş Enerjisi Analizi | Rüzgar Enerjisi Analizi |
| :---: | :---: |
| ![Solar Heatmap](solar_heatmap_final.png) | ![Wind Heatmap](wind_heatmap_fixed.png) |

---
*Geliştirici: [Akif]*
*Bu proje, yenilenebilir enerji dönüşümünü veriye dayalı kararlarla hızlandırmayı amaçlamaktadır.*