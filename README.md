# Tampilan Sebelum
![sebelum](sebelum.png)
```
<ion-header [translucent]="true">
    <ion-toolbar>
        <ion-title>Data Mahasiswa</ion-title>
    </ion-toolbar>
</ion-header>
<ion-content [fullscreen]="true">
<ion-header collapse="condense">
    <ion-toolbar>
        <ion-title size="large">Data Mahasiswa</ion-title>
    </ion-toolbar>
</ion-header>
<!-- button tambah -->
<ion-card>
    <ion-button (click)="openModalTambah(true)" expand="block">Tambah Mahasiswa</ion-button>
</ion-card>
```
# Tampilan Tambah
 ![tambah](tambah.png)
# Tampilan Sesudah Tambah
 ![sesudah_tambah](sesudah_tambah.png)
```
<!-- modal tambah -->
<ion-modal [isOpen]="modalTambah" (ionModalDidDismiss)="cancel()">
    <ng-template>
    <ion-header>
        <ion-toolbar>
        <ion-buttons slot="start">
            <ion-button (click)="cancel()">Batal</ion-button>
        </ion-buttons>
        <ion-title>Tambah Mahasiswa</ion-title>
        </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
        <ion-item>
        <ion-input label="Nama Mahasiswa" labelPlacement="floating" required [(ngModel)]="nama"
            placeholder="Masukkan Nama Mahasiswa" type="text">
        </ion-input>
        </ion-item>
        <ion-item>
        <ion-input label='Jurusan Mahasiswa' labelPlacement="floating" required [(ngModel)]="jurusan"
            placeholder="Masukkan Jurusan Mahasiswa" type="text">
        </ion-input>
        </ion-item>
        <ion-row>
        <ion-col>
            <ion-button type="button" (click)="tambahMahasiswa()" color="primary" shape="full" expand="block">TambahMahasiswa</ion-button>
        </ion-col>
        </ion-row>
    </ion-content>
    </ng-template>
</ion-modal>
```

# Tampilan Edit
 ![edit](edit.png)
# Tampilan Sesudah Edit
 ![sesudah_edit](sesudah_edit.png)
```
<!-- ini untuk modal edit -->
<ion-modal [isOpen]="modalEdit" (ionModalDidDismiss)="cancel()">
    <ng-template>
    <ion-header>
        <ion-toolbar>
        <ion-buttons slot="start">
            <ion-button (click)="cancel()">Batal</ion-button>
        </ion-buttons>
        <ion-title>Edit Mahasiswa</ion-title>
        </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
        <ion-item>
        <ion-input label="Nama Mahasiswa" labelPlacement="floating" required [(ngModel)]="nama"
            placeholder="Masukkan Nama Mahasiswa" type="text">
        </ion-input>
        </ion-item>
        <ion-item>
        <ion-input label='Jurusan Mahasiswa' labelPlacement="floating" required [(ngModel)]="jurusan"
            placeholder="Masukkan Jurusan Mahasiswa" type="text">
        </ion-input>
        </ion-item>
        <ion-input required [(ngModel)]="id" type="hidden">
        </ion-input>
        <ion-row>
        <ion-col>
            <ion-button type="button" (click)="editMahasiswa()" color="primary" shape="full" expand="block">EditMahasiswa</ion-button>
        </ion-col>
        </ion-row>
    </ion-content>
    </ng-template>
</ion-modal>
<ion-card *ngFor="let item of dataMahasiswa">
    <ion-item>
    <ion-label>
        {{item.nama}}
        <p>{{item.jurusan}}</p>
    </ion-label>
    <ion-button color="danger" slot="end" (click)="hapusMahasiswa(item.id)">Hapus</ion-button>
    <ion-button expand="block" (click)="openModalEdit(true,item.id)">Edit</ion-button>
    </ion-item>
</ion-card>
</ion-content>
```