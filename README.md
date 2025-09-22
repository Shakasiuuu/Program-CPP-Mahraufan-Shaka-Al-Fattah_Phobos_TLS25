# Lost and Found Program oleh Mahraufan Shaka Al Fattah_Phobos
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main() {
    long long t;
    cout << "Masukkan waktu t: ";
    cin >> t;

    // Hitung n sesuai flowchart
    int n = (t - 25) % 103;
    if (n < 0) n += 103; // agar selalu positif

    // Buat tabel warna persis
    vector<string> lights(103, "Red");
    for (int i = 0; i <= 19; i++) lights[i] = "Green";
    for (int i = 20; i <= 22; i++) lights[i] = "Yellow";
    for (int i = 23; i <= 102; i++) lights[i] = "Red"; // jelas untuk range Red

    cout << "n = " << n << " → Lampu: " << lights[n] << endl;
    cout << "Program selesai,terima kasih\n";
    return 0;
}
