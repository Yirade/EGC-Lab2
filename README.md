# Tema 2 - OpenTK

## Cerința 1 - Crearea unui proiect elementar

Am creat un proiect elementar utilizând biblioteca OpenTK, urmărind exemplul furnizat în `OpenTK_console_sample01` și `OpenTK_console_sample02`. Am acordat atenție setării viewport-ului. Am modificat valoarea constantei `MatrixMode.Projection` pentru a observa diferențele în modul în care matricea de proiecție este utilizată.

## Cerința 2 - Implementarea controlului obiectului renderizat

Am implementat controlul obiectului renderizat în două moduri:
- Prin apăsarea a două taste: Am utilizat `KeyboardState` pentru a verifica dacă anumite taste sunt apăsate sau eliberate. Am actualizat poziția sau comportamentul obiectului renderizat în funcție de aceste acțiuni ale utilizatorului.
- Prin mișcarea mouse-ului: Am utilizat `MouseState` pentru a controla mișcarea mouse-ului și clicurile. Obiectul renderizat poate fi ascuns sau afișat în funcție de aceste acțiuni.

## Cerința 3 - Răspunsurile la întrebări

1. **Ce este un viewport?**
   Un viewport este o regiune dreptunghiulară în interiorul ferestrei de randare OpenGL în care va fi afișată scena 3D. Definește ce porțiuni ale ferestrei vor fi utilizate pentru randare. Viewport-urile sunt importante pentru gestionarea mai multor ferestre sau pentru efecte cum ar fi "split-screen".

2. **Ce reprezintă conceptul de frames per second din punctul de vedere al bibliotecii OpenGL?**
   Conceptul de frames per second (FPS) în OpenGL reprezintă numărul de cadre (imagini) pe care sistemul le poate genera și afișa pe ecran într-o secundă. Un FPS ridicat indică o animație fluidă, în timp ce un FPS scăzut poate duce la încetiniri în animație.

3. **Când este rulată metoda OnUpdateFrame()?**
   Metoda `OnUpdateFrame()` este rulată la începutul fiecărui cadru (frame) înainte de randare. Aici se gestionează de obicei logica jocului, cum ar fi input-ul utilizatorului sau calculul fizicii.

4. **Ce este modul imediat de randare?**
   Modul imediat de randare este un abordaj de randare în OpenGL în care obiectele sunt desenate unul câte unul folosind apeluri imediate precum `GL.Begin()` și `GL.Vertex()`. Este considerat învechit în OpenGL modern din cauza numărului mare de apeluri de funcții și nu se mai recomandă pentru proiecte noi.

5. **Care este ultima versiune de OpenGL care acceptă modul imediat?**
   Ultima versiune de OpenGL care acceptă modul imediat este OpenGL 3.2, dar este deprecata și nu ar trebui să fie utilizată în proiecte noi.

6. **Când este rulată metoda OnRenderFrame()?**
   Metoda `OnRenderFrame()` este rulată după `OnUpdateFrame()` și este locul în care are loc randarea efectivă a scenei 3D. Aici se desenează obiectele și scena devine vizibilă.

7. **De ce este necesară executarea metodei OnResize() cel puțin o dată?**
   Metoda `OnResize()` trebuie să fie executată cel puțin o dată pentru a actualiza viewport-ul și matricea de proiecție atunci când se creează sau se redimensionează fereastra de randare. Acest lucru asigură afișarea corectă a scenei.

8. **Ce reprezintă parametrii metodei CreatePerspectiveFieldOfView() și care este domeniul lor de valori?**
   Parametrii metodei `CreatePerspectiveFieldOfView()` reprezintă matricea de proiecție perspectivă. Primul parametru este câmpul vizual (fov), care reprezintă unghiul de vizualizare în radiani. Al doilea parametru este raportul de aspect (aspect ratio), care reprezintă raportul dintre lățime și înălțime. Al treilea și al patrulea parametru reprezintă distanța minimă și maximă față de punctul de vedere. Acești parametri influențează modul în care scena 3D este proiectată pe fereastră. Intervalul de valori obișnuit pentru câmpul vizual (fov) este între 0 și Pi (180 de grade), în timp ce raportul de aspect poate fi orice valoare pozitivă. Celelalte parametri sunt de obicei valori pozitive.
