# FirstDB

1° Creare una cartella con cognome.nome.4H.Firstdb

2° Lanciare il visual studio code e aprire la cartella appena creata

3° Lanciare un terminale

4° Copiare il seguente comando nel terminale

``` 
dotnet new console 
```

5° Una volta terminata la creazione della console aprire Program.cs

6° Ora cliccare <a href = "https://www.sqlitetutorial.net/sqlite-sample-database/">qui</a>, si aprirà la pagina dove sarà possibile scaricare il database di prova che si troverà nella sezione Download SQLite sample database, quindi scaricarlo

7° Una volta scaricato spostarlo nella stessa cartella del nostro progetto

8° Riaprire la finestra Visual Studio Code aperta in precedenza 

9° Installare il plugin per visual studio code di nome SQLite, la cui icona è riportata qui sotto

<img 
src="https://user-images.githubusercontent.com/116791222/234798006-06c01e35-cd3f-4772-ab83-5b305904634a.png"
/>

10° Fare pulsante destro su chinook.db da dentro Visual Studio Code e cliccare "Open Databse"

11° Ora entrare nel csproj e cercare `<PackageReference Include="sqlite-net-pc1" Version="1.8.116"`
 
12° Se non è presente copiare e incollare il seguente comando nel terminale:

```
dotnet add package sqlite-net-pcl
``` 

13° Copiare e incollare il seguente codice nel proprio programma e successivamente scrivere nel terminale `dotnet run`:

```
using SQLite;

//Connessione al Database
SQLiteConnection cn1 = new SQLiteConnection("chinook.db");

//Richieste al Database
var tblArtists = cn1.Query<Artist>("select * from artists");

//Stampa su console di quanti record sono presenti in tblArtists
Console.WriteLine($"In questa tabella ci sono {tblArtists.Count} record!");

//Classe di contenimento dei dati
public class Artist
{
    public int ArtistId{get;set;}
    public string Name{get;set;}
}
```

== !!Ricordo che SQLite non è un Databse, ma una libreria!! ==
