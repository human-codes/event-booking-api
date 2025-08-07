# event-booking-api

# Event Booking API

Ushbu loyiha Spring Boot asosida qurilgan bo'lib, tadbirlarni bron qilish uchun RESTful API taqdim etadi. U foydalanuvchilarni boshqarish, autentifikatsiya (JWT yordamida) va tadbirlarni boshqarish funksiyalarini o'z ichiga oladi.

## Loyihani ishga tushirish yo'riqnomasi

Loyihani mahalliy kompyuteringizda ishga tushirish uchun quyidagi qadamlarni bajaring:

### 1. Talablar

*   **Java Development Kit (JDK) 17 yoki undan yuqori versiyasi**
*   **Maven 3.x**
*   **PostgreSQL ma'lumotlar bazasi**
*   **Git**

### 2. Loyihani klonlash

Loyihani GitHub'dan klonlang:

\`\`\`bash
git clone <sizning_github_repository_havolangiz>
cd event-booking-api
\`\`\`

### 3. Ma'lumotlar bazasini sozlash

1.  PostgreSQL serveringizda yangi ma'lumotlar bazasi yarating (masalan, `eventbooking_db`).
2.  `src/main/resources/application.properties` (yoki `application.yml`) faylini oching va ma'lumotlar bazasi ulanish sozlamalarini o'zingiznikiga moslang:

    ```properties
    spring.datasource.url=jdbc:postgresql://localhost:5432/eventbooking_db
    spring.datasource.username=your_username
    spring.datasource.password=your_password
    spring.jpa.hibernate.ddl-auto=update
    spring.jpa.show-sql=true
    \`\`\`
    `your_username` va `your_password` o'rniga o'zingizning PostgreSQL foydalanuvchi nomingiz va parolingizni kiriting.

### 4. Loyihani qurish va ishga tushirish

Maven yordamida loyihani qurish va ishga tushirish uchun quyidagi buyruqlarni bajaring:

\`\`\`bash
mvn clean install
mvn spring-boot:run
\`\`\`

Loyihaning ishga tushganini ko'rsatuvchi loglarni ko'rasiz. Odatda, API `http://localhost:8080` manzilida ishlaydi.

## Texnologiyalar ro'yxati

Ushbu loyiha quyidagi asosiy texnologiyalar va kutubxonalardan foydalanadi:

*   **Spring Boot 3.2.5**: Tezkor va oson Spring ilovalarini yaratish uchun freymvork.
*   **Spring Security**: Autentifikatsiya va avtorizatsiya uchun kuchli freymvork.
*   **JWT (JSON Web Tokens)**: Foydalanuvchi autentifikatsiyasi uchun token asosidagi mexanizm.
    *   `io.jsonwebtoken:jjwt-api`
    *   `io.jsonwebtoken:jjwt-impl`
    *   `io.jsonwebtoken:jjwt-jackson`
*   **Spring Data JPA**: Ma'lumotlar bazasi bilan ishlash uchun ORM (Object-Relational Mapping).
*   **PostgreSQL**: Relyatsion ma'lumotlar bazasi.
*   **Lombok**: Boilerplate kodni kamaytirish uchun kutubxona.
*   **Springdoc OpenAPI UI**: RESTful API hujjatlarini avtomatik yaratish va interaktiv UI (Swagger UI) taqdim etish uchun.
*   **Maven**: Loyiha qurish va bog'liqliklarni boshqarish vositasi.
*   **Java 17**: Dasturlash tili.

## API Endpointlar tavsifi

Loyihaning barcha API endpointlari [Swagger UI](http://localhost:8080/swagger-ui/index.html) orqali hujjatlashtirilgan. Loyihani ishga tushirganingizdan so'ng, brauzeringizda ushbu manzilga o'tib, mavjud endpointlar, ularning parametrlari va javoblarini ko'rishingiz mumkin.

Asosiy API endpointlar quyidagilarni o'z ichiga oladi:

*   **Autentifikatsiya (Authentication)**:
    *   `/api/auth/register`: Yangi foydalanuvchini ro'yxatdan o'tkazish.
    *   `/api/auth/login`: Foydalanuvchini tizimga kiritish va JWT olish.
*   **Foydalanuvchilar (Users)**:
    *   `/api/users`: Foydalanuvchilarni boshqarish (admin huquqlari talab qilinishi mumkin).
*   **Tadbirlar (Events)**:
    *   `/api/events`: Tadbirlarni yaratish, o'qish, yangilash va o'chirish.
*   **Bronlar (Bookings)**:
    *   `/api/bookings`: Tadbirlarga bron qilish va bronlarni boshqarish.

**Swagger UI manzili:**
[http://localhost:8080/swagger-ui/index.html](http://localhost:8080/swagger-ui/index.html)

Postman uchun json fayl project papkasida joylashtirilgan
---

**GitHub havolasi:**
Loyihani GitHub'ga joylashtirganingizdan so'ng, bu yerga o'zingizning GitHub repository havolangizni qo'shing.
