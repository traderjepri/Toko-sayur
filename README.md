# Toko-sayur
Jual beli sayur
class TokoSayur:
    def __init__(self):
        self.sayuran = {}

    def tambah_sayur(self, nama, harga):
        if nama in self.sayuran:
            print(f"{nama} sudah ada di toko.")
        else:
            self.sayuran[nama] = harga
            print(f"{nama} telah ditambahkan dengan harga {harga}.")

    def hapus_sayur(self, nama):
        if nama in self.sayuran:
            del self.sayuran[nama]
            print(f"{nama} telah dihapus dari toko.")
        else:
            print(f"{nama} tidak ditemukan di toko.")

    def lihat_sayuran(self):
        if self.sayuran:
            print("Daftar sayuran di toko:")
            for nama, harga in self.sayuran.items():
                print(f"- {nama}: {harga}")
        else:
            print("Tidak ada sayuran di toko.")

def main():
    toko = TokoSayur()
    
    while True:
        print("\n1. Tambah Sayur")
        print("\n2. Hapus Sayur")
        print("\n3. Lihat Sayuran")
        print("\n4. Keluar")
        
        pilihan = input("Pilih opsi: ")
        
        if pilihan == '1':
            nama = input("Masukkan nama sayur: ")
            harga = float(input("Masukkan harga sayur: "))
            toko.tambah_sayur(nama, harga)
        elif pilihan == '2':
            nama = input("Masukkan nama sayur yang ingin dihapus: ")
            toko.hapus_sayur(nama)
        elif pilihan == '3':
            toko.lihat_sayuran()
        elif pilihan == '4':
            print("Terima kasih telah menggunakan toko sayur!")
            break
        else:
            print("Pilihan tidak valid, silakan coba lagi.")

if __name__ == "__main__":
    main()