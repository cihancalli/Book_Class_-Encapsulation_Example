# Book_Class_Encapsulation_Kotlin_Example

## Kotlin Uygulamasında Book Sınıfı Encapsulation Örneği

```bash
class Book(
    private val author: String, // Yazar ismi (private)
    private val title: String, // Kitap ismi (private)
    private var currentPage: Int = 1 // Mevcut sayfa (private, varsayılan değer 1)
) {

    // Public fonksiyonlar:

    fun getAuthor(): String { // Yazar ismini alma
        return author
    }

    fun getTitle(): String { // Kitap ismini alma
        return title
    }

    fun getCurrentPage(): Int { // Mevcut sayfayı alma
        return currentPage
    }

    fun turnPage() { // Bir sayfa çevirme
        currentPage++
    }

    fun goToPage(pageNumber: Int) { // Belirli bir sayfaya gitme
        if (pageNumber > 0 && pageNumber <= getNumberOfPages()) {
            currentPage = pageNumber
        } else {
            throw IllegalArgumentException("Sayfa numarası geçersiz: $pageNumber")
        }
    }

    fun getNumberOfPages(): Int { // Sayfa sayısını hesaplama (varsayılan olarak 100)
        return 100 // TODO: Gerçek sayfa sayısını hesaplama işlemi burada uygulanacak
    }

    // Private fonksiyonlar:

    // ... (Örnek: Sayfa sayısını hesaplama işleminin detayları)

}

// Örnek kullanım

val book = Book("Yazar Adı", "Kitap Adı")

println("Yazar: ${book.getAuthor()}")
println("Kitap Adı: ${book.getTitle()}")

book.turnPage()
println("Mevcut Sayfa: ${book.getCurrentPage()}")

book.goToPage(50)
println("Mevcut Sayfa: ${book.getCurrentPage()}")
```
Bu kodda, Book adında bir sınıf oluşturuyoruz ve Encapsulation prensibini uyguluyoruz:

* Özellikler (properties): author, title ve currentPage değişkenleri private olarak tanımlanmıştır. Bu, bu değişkenlere doğrudan erişilemeyeceği anlamına gelir.
* Erişim fonksiyonları (getters and setters): getAuthor(), getTitle(), getCurrentPage() ve turnPage() gibi fonksiyonlar, Book sınıfının özel properties'lerine erişmek ve değiştirmek için kullanılır.
* Doğrulama: goToPage() fonksiyonu, geçersiz sayfa numaraları için bir hata fırlatır.
* Gizleme: Sayfa sayısını hesaplama gibi özel işlemler private fonksiyonlar içerisinde gizlenir.

Bu şekilde, Encapsulation kullanarak kodumuzu daha güvenli, modüler ve test edilebilir hale getiriyoruz.

Not: Bu örnekte sayfa sayısını hesaplama işlemi basit bir şekilde 100 olarak sabitlenmiştir. Gerçek bir uygulamada, bu işlemin kitap içeriğine göre dinamik olarak yapılması gerekir.
