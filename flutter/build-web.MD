# FLUTTER WEB, BUILD DAN LAUNCH DI SERVER

## Build

Ada empat cara build flutter web

1. Meng-complie/mem-build aplikasimu di release mode, menggunakan default/auto option:
```
flutter build web
```
2. Meng-complie/mem-build aplikasimu di release mode, menggunakan default/auto option
```
flutter build web
```
3. Meng-complie/mem-build aplikasimu di release mode, menggunakan Canvaskit renderer
```
flutter build web --web-renderer canvaskit --release
```
4. Meng-complie/mem-build aplikasimu di release mode, menggunakan html renderer
```
flutter build web --web-renderer html --release
```
Sedikit lebih cepat dari yang lain.

## Lokasi Build
```
projectmu/build/web
```

## Upload ke Xampp / lampp -- Local Server
1. copy hasil build mu yang ada pada direktori `projectmu/build/web`, paste ke `xampp/htdocs/` atau jika kamu pakai ubuntu silakan copy ke `/opt/lamp/htdocs`
2. Konfigurasi url
- buka file `index.html` pada folder `web` yang sudah kamu copy tadi.
- Jika ente tidak rename folder **web** , maka silakan cari kode yang seperti di bawah
```
<base href="/" />
```
- ubah menjadi
```
<base href="/web/" />
```
- selanjutnya buka file `flutter_service_worker.js` 
- cari code seperti di bawah
```
...
const RESOURCES = {
  "version.json": "68e52fa89487ece36867bdb56273af4c",
  "index.html": "f6798e8ae1badd54339bd11b8f40f45d",
  "/": "f6798e8ae1badd54339bd11b8f40f45d",
...
```
- ubah menjadi
```
...
const RESOURCES = {
  "version.json": "68e52fa89487ece36867bdb56273af4c",
  "index.html": "f6798e8ae1badd54339bd11b8f40f45d",
  "/web/": "f6798e8ae1badd54339bd11b8f40f45d",
...
```
- cari kode seperti di bawah
```
...
const CORE = [
  "/",
...
```
- rubah menjadi
```
...
const CORE = [
  "/web/",
...
```

selanjutnya silakan hidupkan *local server* dan buka browser lalu ketik `localhost/web`
Semoga bermanfaat.
