~~~dart
void main() {
  // List buah-buahan
  List<String> daftarBuah = ['Apel', 'Mangga', 'Pisang', 'Jeruk'];

  // Operator
  bool containsMangga = daftarBuah.contains('Mangga');
  print('Mengandung Mangga: $containsMangga');

  // Map
  Map<String, double> hargaBuah = {
    'Apel': 25.0,
    'Mangga': 20.0,
    'Pisang': 15.0,
    'Jeruk': 10.0
  };

  // Percabangan
  daftarBuah.forEach((buah) {
    if (hargaBuah[buah]! > 15) {
      print('$buah mahal.');
    } else {
      print('$buah murah.');
    }
  });

  // Set
  Set<String> buahUnik = daftarBuah.toSet();
  print('Buah unik: $buahUnik');

  // Function dengan parameter dan optional parameter
  void printHargaBuah(String buah, {double diskon = 0}) {
    double harga = hargaBuah[buah] ?? 0;
    double hargaAkhir = harga - (harga * diskon);
    print('Harga $buah dengan diskon ${diskon * 100}%: $hargaAkhir');
  }

  printHargaBuah('Apel', diskon: 0.1);
  printHargaBuah('Jeruk');

  // Inner function dan anonymous function
  void prosesBuah(Function(String) aksi) {
    daftarBuah.forEach(aksi);
  }

  prosesBuah((buah) {
    print('Proses buah: $buah');
  });

  // Closure
  Function tambahBuah(String buah) {
    daftarBuah.add(buah);
    return () {
      print('Buah $buah ditambahkan ke daftar.');
    };
  }

  var closure = tambahBuah('Anggur');
  closure();

  // Perulangan
  for (var buah in daftarBuah) {
    print(buah);
  }
}
~~~