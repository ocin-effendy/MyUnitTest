# MyUnitTest
Implementing unit test and UI test

Espresso
Sebelumnya, kita perlu ingat kembali tiga komponen utama dari Espresso:

ViewMatchers (onView(ViewMatcher)), untuk menemukan elemen atau komponen antar muka yang diuji.
ViewActions (perform(ViewAction)), untuk memberikan event untuk melakukan sebuah aksi pada komponen antar muka yang diuji.
ViewAssertions(check(ViewAssertion)), untuk mengecek sebuah kondisi atau state dari komponen yang diuji.


@Before
fun setup(){
    ActivityScenario.launch(MainActivity::class.java)
}

Kode di atas digunakan untuk memerintahkan Activity mana yang akan dijalankan.

onView(withId(R.id.edt_length)).perform(typeText(dummyLength), closeSoftKeyboard())
Perhatikan kode di atas, jika kode di atas dibaca maka jadi seperti ini: Sebuah view dengan id edt_length diberi tindakan input dengan sebuah teks dummyLength dan menutup secara berlahan keyboard Android. Jadi terdapat banyak aksi di dalam komponen Espresso


onView(withId(R.id.btn_save)).check(matches(isDisplayed()))
Jika kode di atas dibaca akan menjadi seperti ini: Memastikan sebuah view dengan id btn_save dalam keadaan tampil.

onView(withId(R.id.btn_save)).perform(click())
Jika kode di atas dibaca, akan menjadi seperti ini: Sebuah view dengan id btn_save diberi aksi klik.

onView(withId(R.id.tv_result)).check(matches(withText(dummyCircumference)))
Jika kode di atas dibaca, akan menjadi seperti berikut: Memastikan sebuah view dengan id tv_result mempunyai teks yang sama dengan dummyCircumference.

onView(withId(R.id.edt_length)).check(matches(hasErrorText(fieldEmpty)))
Jika kode di atas dibaca akan menjadi seperti berikut: Memastikan sebuah view dengan id edt_length mempunyai pesan eror yang sama dengan fieldEmpty.
