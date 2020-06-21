#include<iostream>
#include<iomanip>
#include<string>

#define GOL1 3000
#define GOL2 3500
#define GOL3 4000
#define GOL4 5000
using namespace std;

struct Karyawan{
	string nama;
	string nik;
	int golongan;
	float gajiPerminggu;
	int jamKerja;
	int jamLembur;
	float gajiLembur;
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

void cetakData(Karyawan data[], int &banyak);
void cetakHeadData();
void cetakSemuaKomponen(Karyawan data[],int &banyak);
void hitungGaji(Karyawan data[], int &banyak);
void sorting(Karyawan data[],int &banyak);
void search(Karyawan data[],Karyawan hasil[], int &banyak,char &pilih);

int main(){
	char pilih;
	int n;
	profil();
	cout<<"-=Program Gaji Karyawan CV. ABC=-"<<endl<<endl;
	cout<<"Masukkan Jumlah Karyawan: ";
	cin>>n;
	Karyawan orang[n];
	Karyawan pencarian[n];
	for(int a=0; a<n ; a++){
		
		system("color 0a");
		cout<<"\nData Karyawan "<<a+1<<": "<<endl;
		cout<<"NIK: " ; cin>>orang[a].nik ;
		cout<<"Nama: " ;cin.ignore(); getline(cin,orang[a].nama); 
		cout<<"Golongan(1-4): " ; cin>>orang[a].golongan ;
		cout<<"Jam Kerja Per-Minggu: " ; cin>>orang[a].jamKerja ;
	}
	hitungGaji(orang,n);
	MENU:
	cetakHeadData();
	cetakData(orang,n);
	
	cout<<endl;
	cout<<"1.Urut berdasarkan gaji(DESC)"<<endl;
	cout<<"2.Cari berdasarkan nama"<<endl;
	cout<<"3.Cetak semua komponen data karyawan"<<endl;
	cout<<"Pilihan: ";
	cin>>pilih;
	switch (pilih){
	case '1':
		sorting(orang,n);
		cetakHeadData();
		cetakData(orang,n);
		cout<<"\nKembali? (y/n): ";
		cin>>pilih;
		if(pilih=='y' || pilih=='Y')
		goto MENU;
		break;
	case '2':
		search(orang,pencarian,n,pilih);
		cout<<"\nKembali? (y/n): ";
		cin>>pilih;
		if(pilih=='y' || pilih=='Y')
		goto MENU;	
		break;
	case '3':
		cetakSemuaKomponen(orang,n);
		cout<<"\nKembali? (y/n): ";
		cin>>pilih;
		if(pilih=='y' || pilih=='Y')
		goto MENU;	
		break;
	}

	return 0;
}

void cetakData(Karyawan data[], int &banyak){
	for(int i=0 ; i<banyak ; i++){
		cout<<i+1<<setw(16)<<data[i].nik<<setw(15)<<data[i].nama<<setw(11)<<data[i].golongan
		<<setw(11)<<data[i].jamKerja<<setw(16)<<data[i].gajiPerminggu<<endl;
	}
}

void cetakHeadData(){
	profil();
	cout<<"-------------------------------------------------------------------------------------------------------------"<<endl;
	cout<<"No\tNIK\t\tNama\t\tGol.    Jam Kerja    Gaji Per-Minggu"<<endl;
	cout<<"-------------------------------------------------------------------------------------------------------------"<<endl;

}

void hitungGaji(Karyawan data[], int &banyak){
	for (int i=0 ; i<banyak ; i++){
		if(data[i].jamKerja>40){
			data[i].jamLembur=data[i].jamKerja - 40; //kelebihan dari jamkerja
			data[i].jamKerja=40;	//jamkerja ditetapkan ke 40
		}else{
			data[i].jamLembur=0;
		}
		
		if(data[i].golongan==1){
			data[i].gajiLembur = data[i].jamLembur * (GOL1*1.5);//1,1/2
			data[i].gajiPerminggu = data[i].gajiLembur + data[i].jamKerja * GOL1;
			data[i].jamKerja = data[i].jamKerja + data[i].jamLembur;//mengembalikan jamkerja
		}else if(data[i].golongan==2){
			data[i].gajiLembur = data[i].jamLembur * (GOL2*1.5);//1,1/2
			data[i].gajiPerminggu = data[i].gajiLembur + data[i].jamKerja * GOL2;
			data[i].jamKerja = data[i].jamKerja + data[i].jamLembur;//mengembalikan jamkerja			
		}else if(data[i].golongan==3){
			data[i].gajiLembur = data[i].jamLembur * (GOL3*1.5);//1,1/2
			data[i].gajiPerminggu = data[i].gajiLembur + data[i].jamKerja * GOL3;
			data[i].jamKerja = data[i].jamKerja + data[i].jamLembur;//mengembalikan jamkerja			
		}else if(data[i].golongan==4){
			data[i].gajiLembur = data[i].jamLembur * (GOL4*1.5);//1,1/2
			data[i].gajiPerminggu = data[i].gajiLembur + data[i].jamKerja * GOL4;
			data[i].jamKerja = data[i].jamKerja + data[i].jamLembur;//mengembalikan jamkerja			
		}
	}
}


void search(Karyawan data[],Karyawan hasil[], int &banyak,char &pilih){//mencari sekaligus menampilkan pencarian
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
    cout<<"Tampilkan komponen data karyawan? (y/n): ";
	cin>>pilih;
	if(pilih=='y' || pilih=='Y')
	cetakSemuaKomponen(hasil,a);

}

void cetakSemuaKomponen(Karyawan data[],int &banyak){
	profil();
	cout<<"\n-=Komponen Data Karyawan=-"<<endl;
	for(int i=0;i<banyak;i++){
		cout<<"\n-Karyawan "<<i+1<<endl;
		cout<<"NIK: "<<data[i].nik<<endl;
		cout<<"Nama: "<<data[i].nama<<endl;
		cout<<"Golongan: "<<data[i].golongan<<endl;
		cout<<"Jam Kerja: "<<data[i].jamKerja<<endl;
		cout<<"Jam Lembur: "<<data[i].jamLembur<<endl;
		cout<<"Gaji Lembur: "<<data[i].gajiLembur<<endl;
		cout<<"Gaji Per-minggu(total): "<<data[i].gajiPerminggu<<endl;
	}
}

void sorting(Karyawan data[],int &banyak){
	//insertion sort
	int i,j;
	Karyawan temp;
	for(i=1;i<=banyak-1;i++)
    {
        temp=data[i];
        j=i-1;   //var j sebagai indeks sebelumnya
		 
        while((temp.gajiPerminggu>data[j].gajiPerminggu)&&(j>=0)) //kondisi data ke i kurang dengan data dibelakangnya
        {
            data[j+1]=data[j];    //Menyimpan data ke i ke indeks sebelumnya
            j=j-1;			//assign j batas loop
        }
 
        data[j+1]=temp;    //menyimpan data yang sudah dicek 
    }

}
