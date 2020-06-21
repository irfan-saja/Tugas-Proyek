#include<iostream>
#include<iomanip>
#include<string>
using namespace std;

struct DataMhs{
	string nama;
	string stambuk;
	float nilaiUTS;
	float nilaiUAS;
	float nilaiTugasMandiri;
	float nilaiTugasProyek;
	float nilaiKehadiran;
	float nilaiAkhir;
	string predikat;
	float ipk;
};

void profil()
{
	system("cls");
	cout<<"============================="<<endl;
	cout<<"=== Nama: Muhammad Irfan ==="<<endl;
	cout<<"=== Stambuk: 13020190147  ==="<<endl;
	cout<<"=== Kelas: A3	 	  ==="<<endl;
	cout<<"============================="<<endl;
}
void cetakData(DataMhs data[], int &banyak);
void cetakHeadData();
void cetakPembagianNilai(DataMhs data[],int &banyak);
void hitungNilaiAkhir(DataMhs data[], int &banyak);
void sorting(DataMhs data[],int &banyak);
void search(DataMhs data[],DataMhs hasil[], int &banyak, char &pilih);

int main(){
	char pilih;
	int n;
	profil();
	cout<<"-=Program Menghitung Nilai Mahasiswa=-"<<endl<<endl;
	cout<<"Masukkan Jumlah Data: ";
	cin>>n;
	DataMhs mhs[n];
	DataMhs pencarian[n];
	
	system ("color 0a");
	for(int a=0; a<n ; a++){
		cout<<"Data Mahasiswa "<<a+1<<": "<<endl;
		cout<<"Stambuk: " ; cin>>mhs[a].stambuk ;
		cout<<"Nama: " ;cin.ignore(); getline(cin,mhs[a].nama); 
		cout<<"Nilai UTS: " ; cin>>mhs[a].nilaiUTS ;
		cout<<"Nilai UAS: " ; cin>>mhs[a].nilaiUAS ;
		cout<<"Nilai Tugas Mandiri: " ; cin>>mhs[a].nilaiTugasMandiri ;
		cout<<"Nilai Tugas Proyek: " ; cin>>mhs[a].nilaiTugasProyek ; 
		cout<<"Nilai Kehadiran(*min 90): " ; cin>>mhs[a].nilaiKehadiran ; cout<<endl;
	}
	hitungNilaiAkhir(mhs,n);
	MENU:
	cetakHeadData();
	cetakData(mhs,n);
	
	cout<<endl;
	cout<<"1.Urut berdasarkan nilai akhir(DESC)"<<endl;
	cout<<"2.Cari berdasarkan nama"<<endl;
	cout<<"3.Cetak pembagian nilai semua Mahasiswa"<<endl;
	cout<<"Pilihan: ";
	cin>>pilih;
	switch (pilih){
	case '1':
		sorting(mhs,n);
		cetakHeadData();
		cetakData(mhs,n);
		cout<<"\nKembali? (y/n): ";
		cin>>pilih;
		if(pilih=='y' || pilih=='Y')
		goto MENU;
		break;
	case '2':
		search(mhs,pencarian,n,pilih);
		cout<<"\nKembali? (y/n): ";
		cin>>pilih;
		if(pilih=='y' || pilih=='Y')
		goto MENU;	
		break;
	case '3':
		cetakPembagianNilai(mhs,n);
		cout<<"\nKembali? (y/n): ";
		cin>>pilih;
		if(pilih=='y' || pilih=='Y')
		goto MENU;	
		break;
	}

	return 0;
}


void cetakData(DataMhs data[], int &banyak){
	for(int a=0 ; a<banyak ; a++){
		cout<<a+1<<setw(16)<<data[a].stambuk<<setw(15)<<data[a].nama<<setw(15)<<data[a].nilaiAkhir
		<<setw(11)<<data[a].ipk<<setw(10)<<data[a].predikat<<endl;
	}
}

void cetakHeadData(){ 
	profil();
	cout<<"-------------------------------------------------------------------------------------------------------------"<<endl;
	cout<<"No\tStambuk\t\tNama\t\tNilai Akhir    IPK    Predikat"<<endl;
	cout<<"-------------------------------------------------------------------------------------------------------------"<<endl;

}

void hitungNilaiAkhir(DataMhs data[], int &banyak){
	for (int i=0 ; i<banyak ; i++){
		data[i].nilaiUTS = data[i].nilaiUTS * 20/100;
		data[i].nilaiUAS = data[i].nilaiUAS * 25/100;
		data[i].nilaiTugasMandiri = data[i].nilaiTugasMandiri * 20/100;
		data[i].nilaiTugasProyek = data[i].nilaiTugasProyek * 20/100;
		data[i].nilaiKehadiran = data[i].nilaiKehadiran * 15/100;
		data[i].nilaiAkhir = data[i].nilaiUTS + data[i].nilaiUAS + data[i].nilaiTugasMandiri
		 + data[i].nilaiTugasProyek + data[i].nilaiKehadiran;
		if(data[i].nilaiKehadiran < 13.5 || data[i].nilaiUTS == 0 || data[i].nilaiUAS == 0
		 || data[i].nilaiTugasMandiri == 0 || data[i].nilaiTugasProyek == 0){
		 	data[i].predikat = "E";
			data[i].ipk = 0;	
		} else if(data[i].nilaiAkhir > 85){
			data[i].predikat = "A";
			data[i].ipk = 4.00;
		} else if(data[i].nilaiAkhir >= 81 && data[i].nilaiAkhir<=85){
			data[i].predikat = "A-";
			data[i].ipk = 3.75;
		} else if(data[i].nilaiAkhir >= 76 && data[i].nilaiAkhir<=80.9){
			data[i].predikat = "B+";
			data[i].ipk = 3.50;
		} else if(data[i].nilaiAkhir >= 71 && data[i].nilaiAkhir<=75.9){
			data[i].predikat = "B";
			data[i].ipk = 3.00;
		} else if(data[i].nilaiAkhir >= 66 && data[i].nilaiAkhir<=70.9){
			data[i].predikat = "B-";
			data[i].ipk = 2.75;
		} else if(data[i].nilaiAkhir >= 61 && data[i].nilaiAkhir<=65.9){
			data[i].predikat = "C+";
			data[i].ipk = 2.50;
		} else if(data[i].nilaiAkhir >= 51 && data[i].nilaiAkhir<=60.9){
			data[i].predikat = "C";
			data[i].ipk = 2.00;
		} else if(data[i].nilaiAkhir >= 45 && data[i].nilaiAkhir<=50.9){
			data[i].predikat = "D";
			data[i].ipk = 1.00;
		} else if(data[i].nilaiAkhir <45){
			data[i].predikat = "E";
			data[i].ipk = 0;
		}
	}
}

void sorting(DataMhs data[],int &banyak){
	//insertion sort
	int i,j;
	DataMhs temp;
	for(i=1;i<=banyak-1;i++)
    {
        temp=data[i];
        j=i-1;   //var j sebagai indeks sebelumnya
		 
        while((temp.nilaiAkhir>data[j].nilaiAkhir)&&(j>=0)) //kondisi data ke i kurang dengan data dibelakangnya
        {
            data[j+1]=data[j];    //Menyimpan data ke i ke indeks sebelumnya
            j=j-1;			//assign j batas loop
        }
 
        data[j+1]=temp;    //menyimpan data yang sudah dicek 
    }

}


void search(DataMhs data[],DataMhs hasil[], int &banyak,char &pilih){
	int a=0;
	size_t found;
    string cari;
    cout<<"Masukkan Nama: ";
    cin.ignore(); getline(cin,cari);
    cetakHeadData();
    for(int i=0;i<banyak;i++)
    { 
    	found = data[i].nama.find(cari);
    	if(found != string::npos)
        {
            hasil[a]=data[i];
            a++;
        }
    	
    }
    cetakData(hasil,a);

    cout<<"\nPencarian '"<<cari<<"' menemukan "<<a<<" data"<<endl;
    cout<<"Tampilkan pembagian nilai? (y/n): ";
	cin>>pilih;
	if(pilih=='y' || pilih=='Y')
	cetakPembagianNilai(hasil,a);

}

void cetakPembagianNilai(DataMhs data[],int &banyak){
	profil();
	cout<<"\n-=Pembagian Nilai=-"<<endl;
	for(int i=0;i<banyak;i++){
		cout<<"\n-Mahasiswa "<<i+1<<endl;
		cout<<"Stambuk: "<<data[i].stambuk<<endl;
		cout<<"Nama: "<<data[i].nama<<endl;
		cout<<"Nilai Tugas Mandiri: "<<data[i].nilaiTugasMandiri<<endl;
		cout<<"Nilai Tugas Proyek: "<<data[i].nilaiTugasProyek<<endl;
		cout<<"Nilai UTS: "<<data[i].nilaiUTS<<endl;
		cout<<"Nilai UAS: "<<data[i].nilaiUAS<<endl;
		cout<<"Nilai Kehadiran: "<<data[i].nilaiKehadiran<<endl;
		cout<<"Nilai Akhir(total): "<<data[i].nilaiAkhir<<endl;
		cout<<"IPK: "<<data[i].ipk<<endl;
		cout<<"Predikat: "<<data[i].predikat<<endl;
	}
}
