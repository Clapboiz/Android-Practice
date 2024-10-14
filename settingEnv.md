# TÌM HIỂU ANDROID ENVIRONMENT

| Settings up a testing enviroment

| Thực hiện: Clapboiz

# TABLE OF CONTENTS
1. [Android Studio](#1-android-studio)

2. [Emulator](#2-emulator)

3. [References](#3-references)

# CONTENTS
## 1. ANDROID STUDIO

Sau khi tải `android studio` trên trang chủ của nó thì tiến hành tạo 1 chương trình cơ bản.

![image](https://github.com/user-attachments/assets/fb4f2800-2ca2-4660-bf88-74185bf77547)

Đây là giao diện khi chúng ta mới mở ứng dụng lên. Nếu mà chúng ta đã từng tạo project trên android studio thì nó sẽ hiển thị như vậy, còn nếu chưa tạo thì nó sẽ trắng tinh.

![image](https://github.com/user-attachments/assets/bf6ccf1f-14d0-4741-b149-3fc904309aad)

Chúng ta có thể open project hoặc tạo project, thì ở đây ta hãy tạo 1 project mới. Và khi bấm create project thì nó hiện ra 1 số `template activity`.

Thì sơ qua activity là gì? Activity trong Android là một thành phần đại diện cho một màn hình giao diện mà người dùng có thể tương tác trong ứng dụng. Nó quản lý vòng đời của giao diện và các tương tác của người dùng.

Ở đây chúng ta có thể chọn bất kì cái nào mà phù hợp với nhu cầu của chúng ta. Trong trường hợp này tôi chọn `no activity` để làm vì không có cái nào phù hợp nhu cầu.

![image](https://github.com/user-attachments/assets/ec50a69a-eb95-4de9-bdb6-8939e39fd844)

Và những option trên bạn có thể chọn theo ý mình, giống như các ide khác như vs, vscode,...

![image](https://github.com/user-attachments/assets/ebc2b0f4-4251-4fd5-8474-b3c2ecfe11a4)

Tiến hành chuột phải vào và chọn empty activity.

![image](https://github.com/user-attachments/assets/d73c19bf-541e-4a9d-9b81-90942b908ff8)

![image](https://github.com/user-attachments/assets/e2db8097-c7d5-4507-a5e6-f0e54ba5fbe7)

Và sau khi tạo thì nó được file `MainActivity`.

File MainActivity trong Android là Activity chính, đại diện cho màn hình của ứng dụng. Nó quản lý giao diện và xử lý sự kiện người dùng. Đây là nơi bạn viết code để hiển thị UI và xử lý các tương tác trong ứng dụng.

AndroidManifest.xml khai báo thành phần, quyền, và cấu hình chính của ứng dụng, đồng thời chỉ định Activity khởi chạy đầu tiên.

![image](https://github.com/user-attachments/assets/6a5a87d8-f721-469c-88a3-a0222eb135b8)

Đây là file chứa định nghĩa chính về giao diện của ứng dụng.

![image](https://github.com/user-attachments/assets/035e09e6-0cbd-4e45-8154-896f52404d01)

Đoạn mã code trên định nghĩa MainActivity trong ứng dụng Android:

```
android:name=".MainActivity": Đặt tên cho activity.
android:exported="true": Cho phép activity này được khởi động từ bên ngoài (từ launcher).

<intent-filter>: Xác định rằng đây là activity chính:
<action android:name="android.intent.action.MAIN" />: Xác định đây là action khởi động.
<category android:name="android.intent.category.LAUNCHER" />: Đưa activity vào danh sách ứng dụng (launcher).
```

![image](https://github.com/user-attachments/assets/78d32598-95bb-4aba-9788-0c7b3985d29f)

Tiến hành vào `device manager` để tạo device.

Sau khi tạo thì ta có thể run app

![image](https://github.com/user-attachments/assets/9505b7ea-6bcc-491a-88c5-19d5b5bc6322)

## 2. EMULATOR
Ở trong bài này thì chúng ta dùng emulator genymotions, hiện có rất nhiều emulator bao gồm bluestack, genymotions, ... hoặc những emulator tương tự.

Tiến hành tải genymotion từ trang chủ của nó, hãy nhớ tải virtual box nữa nhé.

Sau khi tải về thì tiến hành mở nó lên.

![image](https://github.com/user-attachments/assets/8ebf65fd-c216-423d-9c1b-ab84a8e6e6ca)

Bấm vào dấu + và tiến hành tạo device, ta có thể tùy chỉnh theo mục đích sử dụng như loại máy, api version, ...

Sau khi tạo xong thì khởi động lên và dùng như 1 chiếc điện thoại bình thường.

Bây giờ thì tiến hành `Configuring Genymotion to BurpSuite`.

Mở burp lên và gõ `http://burp/`, sau đó download `CA Certificate`

![image](https://github.com/user-attachments/assets/6ab7f0b7-efa1-4f71-956f-b9733bb0c714)

Tiến hành copy file `cacert.der` vào trong genymotion.

![image](https://github.com/user-attachments/assets/4e750702-2e1d-41f2-9e94-4ce2d0b9f61e)

Sau đó vào wifi và nhấn giữ chuột vào `androidwifi` và bấm modify. Lưu ý phải nhấn giữ chuột (lưu ý phải đổi đuôi file về dạng `.crrt` hoặc `.cer`, dạng `.der` sẽ không được hỗ trợ).

![image](https://github.com/user-attachments/assets/8b4f18d1-7ffa-4911-a3ee-9fca11405659)

Install thành công cert thì follow theo trang này step by step k sót bước nào:

```
https://www.genymotion.com/blog/tutorial/burp-suite-genymotion-device-image/
```

Sau khi làm hết thì sẽ bắt được request bằng burpsuite.

## 3. REFERENCES
[1]. https://ultahost.com/knowledge-base/install-android-studio-on-windows/

[2]. https://www.genymotion.com/blog/tutorial/burp-suite-genymotion-device-image/
