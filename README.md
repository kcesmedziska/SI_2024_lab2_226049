Калина Чешмеџиска 226049

2. ![CFG lab2](https://github.com/kcesmedziska/SI_2024_lab2_226049/assets/119429486/9d3eb095-0d5c-4645-a00f-1ee715c08e28)

3. За пресметување на цикломатската комплексност ја користиме формулата: V(G) = E - N + 2P и според Control Flow Graph ги броиме ребрата и јазлите на кодот. Е - бројот на ребрата е 12, N - бројот на јазлите е 10 и Р - бројот на поврзани компоненти е 1. 
Според формулата V(G) = E - N + 2P добиваме: 
V(G) = 12 - 10 + 2*1   
V(G) = 12 - 10 + 2
V(G) = 4
Цикломатската комплексност на кодoт изнесува 4.
4. Според Every Branch критериумот треба да ги изминеме сите гранки во кодот, со Control Flow Graph ги идентификуваме гранките: if (allItems == null), if (item.getName() == null || item.getName().length() == 0), if (item.getBarcode() != null) и if (sum <= payment).
- За првата гранка if (allItems == null):
Тест случај 1: allItems == null, payment == 100 -> true, каде се проверува дали функцијата ќе фрли исклучок кога allItems е null. 
Тест случај 2: allItems != null, payment == 100 -> false, каде се проверува дали функцијата ќе продолжи со извршување кога allItems не е null
- За втората гранка item.getName() == null || item.getName().length() == 0: 
Тест случај 3: item.getName() == null, item.getBarcode() == "12345", item.getPrice() = 50, item.getDiscount() = 0.1, payment == 100 -> true, каде се проверува дали фукнцијата ќе постави име на предметот кога името е null или празен стринг.
Тест случај 4: item.getName() != null, item.getName().length != 0, item.getBarcode() != "12345", item.getPrice() = 50, item.getDiscount() = 0.1, payment == 100 -> false, каде се проверува дали функцијата ќе продолжи со извршување кога името на предметот не е null или празен стринг.
- За третата гранка item.getBarcode() != null:
Тест случај 5: item.getBarcode() == null, payment == 100 -> false, каде се проверува дали функцијата ќе фрли исклучок кога баркодот на предметот е null 
Тест случај 6: ite.getBarcode() == "12345", item.getPrice() == 50, item.getDicount() == 0.1, payment == 100 -> true, каде се проверува дали функцијата ќе продолжи со извршување кога баркодот на предметот не е null.
- За четвртата гранка sum <= payment:
Тест случај 7: sum == 100, payment == 100 -> true, каде се проверува дали функцијата ќе врати true кога уплатената сума е доволна за купување на предметите.
Тест случај 8: sum == 150, payment == 100 -> false, каде се проверува дали функцијата ќе врати false кога уплатената суме не е доволна за купување на предметите.
 5. Според Multiple Condition критериумот  треба да ги покриеме сите можни комбинации на условите во еден if израз.
Во случајот на условот if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0'), треба да ги разгледаме комбинациите:
- Тест случај 1: item.getPrice() == 400, item.getDiscount() == 0.1, item.getBarcode().charAt(0) == '0' -> true, true, true, каде сите три услови се вистинити па треба да се изврши if условот.
- Тест случај 2: item.getPrice() == 400, item.getDiscount() == 0.1, item.getBarcode().charAt(0) == '0' -> true, true, false, каде првиот и вториот услов се вистинит, а третиот е лажен, па не треба да се изврши if условот.
- Тест случај 3: item.getPrice() == 400, item.getDiscount() == 0, item.getBarcode().charAt(0) == '0' -> true, false, true, каде првиот и третиот услов се вистинити, а вториот е лажен, па не треба да се изврши if условот.
- Тест случај 4: item.getPrice() == 300, item.getDiscount() == 0.1, item.getBarcode().charAt(0) == '0' -> false, true, true, каде вториот и третиот услов се вистинити, а првиот е лажен, па if условот не треба да се изврши. 
- Тест случај 5: item.getPrice() == 300, item.getDiscount() == '0', item.getBArcode().charAt(0) == '0' -> false, false, true, каде сите три услови се лажни, па if условот не треба да се изврши.
