# SI_2022_lab2_203002

Мила Андоновиќ 203002

----------------------------------

*CFG

![CFG drawio](https://user-images.githubusercontent.com/86725352/171935208-1b4dc9f8-b8d5-4473-bc1c-5b2880c8f027.png)

----------------------------------

*Цикломатска комплексност

 I) начин
М = Р+1
Р - број на предикатни јазли
М - Цикломатска комплексност

P e 8. 8 предикатни јазли и + 1 што се додава.
М = 8 + 1 = 9.
Цикломатската комплексност е 9.


 II) начин
 М = E + N + 2*P
E = број на ребра 
N = број на јазли 
P = број на повржани компоненти
Е = 31
N = 24
P = 1
М = 31 - 24 + 2*1 = 31 - 24 + 2 = 7 + 2 = 9

----------------------------------

*Every Statement

void everyStatementsTest()
{ 
        IllegalArgumentException ex = assertThrows(IllegalArgumentException.class, () -> SILab2.function(List.of()));
        assertTrue(ex.getMessage().contains("List length should be greater than 0"));
//vo ovoj slucaj dolzina na nizata e 0 i se ispolnuva uslovot i se frla Exception sto ja zavrsuva programata
        ex = assertThrows(IllegalArgumentException.class, () -> SILab2.function(List.of("x", "#", "x", "#", "#", "x", "x")));
        assertTrue(ex.getMessage().contains("List length should be a perfect square"));

        List<String> expected = List.of("2", "#", "2", "#", "4", "#", "2", "#", "2");
        List<String> initial = List.of("x", "#", "x", "#", "x", "#", "x", "#", "x");
        assertEquals(SILab2.function(initial), expected);
        
//vo ovoj slucaj nizata ima neparen broj na elementi i se ispolnuva uslovot i se frla Exception sto ja zavrsuva programata
}

----------------------------------

*Every Branch
void everyBranchTest() 
{ 
    IllegalArgumentException ex = assertThrows(IllegalArgumentException.class, () -> SILab2.function(List.of()));
    assertTrue(ex.getMessage().contains("List length should be greater than 0"));

    ex = assertThrows(IllegalArgumentException.class, () -> SILab2.function(List.of("x", "#", "x", "#", "x", "#")));
    assertTrue(ex.getMessage().contains("List length should be a perfect square"));

    List<String> initial = List.of("x", "#", "x", "#", "#", "x", "#", "#", "x", "#", "x", "#", "x", "x", "x", "#");
    List<String> expected = List.of("2", "#", "3", "#", "#", "4", "#", "#", "2", "#", "3", "#", "x", "1", "1", "#");
    assertEquals(SILab2.function(initial), expected);
}
