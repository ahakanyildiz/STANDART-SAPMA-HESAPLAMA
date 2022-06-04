# STANDART-SAPMA-HESAPLAMA
Girilen verilerin aritmetik ortalamasını,varyanslarını ve nihayetinde standart sapmasını alan algoritma



void standartsapma()
{
    Console.WriteLine("Kişi sayısını giriniz..");
    string uye = Console.ReadLine();
    int toplam = 0;
    double ortalama = 0;
    double varyans;
    double varyanstoplam = 0;
    double varyansbolme;
    int[] diziveri = new int[Convert.ToInt32(uye)];
    double[] dizivaryans = new double[Convert.ToInt32(uye)];

    for (int i = 0; i < Convert.ToInt32(uye); i++)
    {
        string a;
        Console.WriteLine((i+1).ToString() + ". veriyi giriniz");
        a = Console.ReadLine();
        diziveri[i] = Convert.ToInt32(a);   
    }

    for (int i = 0; i < Convert.ToInt32(uye); i++)
    {
        toplam += diziveri[i];
    }
    ortalama = toplam / Convert.ToInt32(uye);
    Console.WriteLine("Verilerinizin ortalaması" + ortalama);

    for (int i = 0; i < Convert.ToInt32(uye); i++)
    {
        varyans = (diziveri[i] - ortalama) * (diziveri[i] - ortalama);
        dizivaryans[i] = varyans;
        varyanstoplam += varyans;
    }
    varyansbolme = varyanstoplam / (Convert.ToInt32(uye) - 1);
    double varyans2bsmk = Math.Round(varyansbolme, 2); ;
    Console.WriteLine("Standart sapmanız: " + Math.Sqrt(varyans2bsmk).ToString());
}

standartsapma();
