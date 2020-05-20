import java.util.Scanner;

class ogrenci {

    private String isim;
    private int ogrenciNo;
    private double VizeNotu;
    private double projeNotu;
    private double finalNotu;

    public double GenelNot;

    public void setIsim(String adSoyad) {
        isim = adSoyad;
        System.out.print("İsim: " + isim);
        System.out.println();
    }

    public String getIsim() {
        return isim;
    }

    public void setOgrenciNo(int okulNo) {
        ogrenciNo = okulNo;
        System.out.print("Öğrenci No: " + ogrenciNo);
        System.out.println();
    }

    public int getOgrenciNo() {
        return ogrenciNo;
    }

    public void setVizeNotu(double vizePuani) {
        VizeNotu = vizePuani;
        System.out.print("Vize Notu= " + VizeNotu);
        System.out.println();
    }

    public double getVizeNotu() {
        return VizeNotu;
    }

    public void setProjeNotu(double projePuani) {
        projeNotu = projePuani;
        System.out.println("Proje Notu= " + projeNotu);
        System.out.println();
    }

    public double getProjeNotu() {
        return projeNotu;
    }

    public void setFinalNotu(double FinalPuani) {
        finalNotu = FinalPuani;
        System.out.println("Final Notu= " + finalNotu);
        System.out.println();
    }

    public double getFinalNotu() {
        return finalNotu;
    }

    public double notHesapla(double finalNotu, double projeNotu, double VizeNotu) {

        GenelNot = ((finalNotu * 40) / 100) + ((projeNotu * 35) / 100) + ((VizeNotu * 25) / 100);
        System.out.println("Genel Not ortalamanız= " + GenelNot);

        return GenelNot;

    }

    public void harfNotuCevir() {

        if (GenelNot >= 90 && GenelNot <= 100) {
            System.out.println("Harf notunuz => AA");
        } else if (GenelNot >= 85 && GenelNot <= 89) {
            System.out.println("Harf notunuz => BA");
        } else if (GenelNot >= 75 && GenelNot <= 84) {
            System.out.println("Harf notunuz => BB");
        } else if (GenelNot >= 70 && GenelNot <= 74) {
            System.out.println("Harf notunuz => CB");
        } else if (GenelNot >= 60 && GenelNot <= 69) {
            System.out.println("Harf notunuz => CC");
        } else if (GenelNot >= 55 && GenelNot <= 59) {
            System.out.println("Harf notunuz => DC");
        } else if (GenelNot >= 50 && GenelNot <= 54) {
            System.out.println("Harf notunuz => DD");
        } else if (GenelNot >= 0 && GenelNot <= 49) {
            System.out.println("Harf notunuz => FF");
        }
    }

}

public class ogrenciTest {

    public static void main(String[] args) {

        // Bu soruyu örneğin 30 kişilik bir sınıf için yapmak istiyorsanız for döngüsünü veya while döngüsünü kullanarak yapabilirsiniz. Döngü içerisine almanız gereken kısım ise aşağıda kullanıcıdan aldığımız veriler ve metotlara eriştiğimiz ksıımlar olacaktır.
        ogrenci o1 = new ogrenci();

        Scanner klavye = new Scanner(System.in);

        System.out.print("Lütfen adınızı giriniz: ");
        String isim = klavye.nextLine();
        o1.setIsim(isim);

        System.out.print("Okul numaranızı giriniz: ");
        int OkulNo = klavye.nextInt();
        o1.setOgrenciNo(OkulNo);

        System.out.print("Vize notunuzu giriniz: ");
        int vizePuan = klavye.nextInt();
        o1.setVizeNotu(vizePuan);

        System.out.print("Proje notunuzu giriniz: ");
        int projePuan = klavye.nextInt();
        o1.setProjeNotu(projePuan);

        System.out.print("Final notunuzu giriniz: ");
        int FinalNot = klavye.nextInt();
        o1.setFinalNotu(FinalNot);

        o1.notHesapla(FinalNot, projePuan, vizePuan);
        o1.harfNotuCevir();

    }

}