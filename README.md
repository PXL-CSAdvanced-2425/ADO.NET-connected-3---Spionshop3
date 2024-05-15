# Spionshop 3

Maak een toepassing om de spionnen op te zoeken uit een bepaalde stad.

De toepassing zoekt ook de verschillende categorieën in de DB Spion en
geeft die weer in een listbox. In een DataGrid worden de artikelen uit
de geselecteerde categorie geselecteerd. De database Spionshop bevindt
zich op de SQL Server.

Wanneer je de toepassing opstart, wordt onderstaande gegevens getoond.

***Start Windows***

![Afbeelding met schermopname, ontwerp Automatisch gegenereerde
beschrijving](./media/image1.png)

Je kan in het tekstvak *TxtWoonplaats* een plaats opzoeken waar de
spionnen actief zijn.

Vb. *L\...* of *Lo...* of *Lon\...* volstaat om de spionnen uit Londen
weer te geven in een listbox *LstWoonplaats*. De listbox *LstCategorie*
haalt de artikels uit de geselecteerde categorie op en toont ze in de
DataGrid *DgdArtikel*.

***Selectie van Lo en categorie Algemeen.***

![Afbeelding met tekst, software, Computerpictogram, schermopname
Automatisch gegenereerde
beschrijving](./media/image2.png)

***Programmeervoorwaarden***

-   Bij de Load wordt gebruikt gemaakt van
    de klasse Categorie en de Stored Procedure *ArtikeluitCategorie* om
    de verschillende categorieën uit de database op te halen en in de
    listbox *LstCategorie* toe te voegen.
    
![Afbeelding met tekst, schermopname, Lettertype, nummer Automatisch
    gegenereerde
    beschrijving](./media/image3.png)
    
-   Maak een Stored Procedure aan in SQL Server om de artikels van een
    opgegeven categorie op te halen.

```
CREATE PROCEDURE [dbo].[ArtikelUitCategorie]
	@CatID smallint
AS
	SELECT artikel, omschrijving, verkoopprijs
	FROM artikel
	WHERE cat_id = @CatID
	ORDER BY artikel
```
