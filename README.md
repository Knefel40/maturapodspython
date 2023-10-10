liczba_kobiet = 0
liczba_mez =0
listopad =0
with open("dane.txt") as dane:
    for wiersz in dane:
        pesel = wiersz.strip();
        miesiac = int(pesel[2:4])
        if int(pesel[-2])%2==0:
            liczba_kobiet=liczba_kobiet+1
        if pesel[-2] in["1","3","5","7","9"]:
            liczba_mez=liczba_mez+1
        if miesiac == 11 or miesiac == 31:
            listopad+=1
        liczba_kontrol = 0
        mnozniki = [1,3,7,9,1,3,7,9,1,3,1]
        for i in range(len(pesel)):
            liczba_kontrol+=mnozniki[i]*int(pesel[i])
        if liczba_kontrol%10!=0:
            print(pesel)
        #print(pesel,pesel[-2])
print("liczba mezczyzn",liczba_mez)
print("liczba kobiet",liczba_kobiet)
print("liczba osob z listopada",miesiac)


