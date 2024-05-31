# Tutorial 1 Modul 11

<details>
<summary>Hello Minikube</summary>

1. Sebelum mengekspos aplikasi sebagai layanan, kita dapat melihat log yang terkait dengan aplikasi itu sendiri yang berjalan dalam kontainer Docker. Log ini bisa mencakup pesan _startup_, setiap kesalahan atau peringatan yang ditemukan selama eksekusi, dan informasi relevan lainnya yang dihasilkan oleh aplikasi.

    Setelah mengekspos aplikasi sebagai layanan dan mengaksesnya melalui _proxy_ yang berjalan di Minikube menggunakan `kubectl`, log kemungkinan akan menunjukkan aktivitas tambahan terkait komunikasi jaringan dan permintaan yang ditangani oleh layanan. Setiap kali aplikasi dibuka melalui _proxy_, akan ada peningkatan jumlah log yang mencerminkan permintaan masuk, pemrosesan permintaan tersebut oleh layanan, dan setiap respons yang dikirim kembali ke klien.

    Jumlah log akan meningkat setiap kali kita membuka aplikasi, karena setiap interaksi memicu aktivitas log sebagai respons terhadap permintaan masuk dan pemrosesan permintaan tersebut oleh layanan. Peningkatan log ini memberikan indikasi yang jelas tentang aktivitas layanan dan responsivitasnya terhadap permintaan klien.

2. Opsi `-n` dalam `kubectl get` digunakan untuk menentukan _namespace_, letak dari sumber daya akan didaftarkan. _Namespace_ Kubernetes menyediakan cara untuk membagi sumber daya kluster secara logis dan memungkinkan banyak pengguna atau tim untuk berbagi kluster yang sama tanpa saling mengganggu. Ketika tidak ada _namespace_ yang ditentukan, kubectl biasanya otomatis menggunakan _namespace_ _default_.

    Dalam tutorial, panggilan pertama `kubectl get` tidak menyertakan opsi `-n`, jadi itu mencantumkan sumber daya dari _namespace default_ yang mungkin tidak termasuk sumber daya yang kita buat secara eksplisit jika kita membuatnya di _namespace_ yang berbeda.

    Panggilan kedua `kubectl get` menyertakan opsi `-n` dengan nilai yang diatur ke `kube-system` sehingga mencantumkan sumber daya khusus dari _namespace_ `kube-system`. _Namespace_ ini biasanya berisi komponen sistem Kubernetes dan sumber daya terkait infrastruktur.

    Jika kita secara eksplisit membuat _pod_ dan layanan di _namespace_ yang berbeda, kita perlu menentukan _namespace_ tersebut menggunakan opsi `-n` dalam `kubectl get` untuk melihat sumber daya tersebut tercantum dalam _output_. Misalnya:

        
        kubectl get pods,services -n <namespace>
        

    Ubah `<namespace>` dengan nama yang kita inginkan. Ini akan mendaftarkan _pods_ dan layanan secara spesifik dari _namespace_ tersebut. Jika kita membuat _resources_ pada `default` _namespace_ dan ingin melihatnya, kita bisa menghapus `-n` dari perintah di atas.

</details>

<details>
<summary>Rolling Update Deployment</summary>



</details>