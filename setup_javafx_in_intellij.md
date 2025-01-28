Вот подробная инструкция по добавлению JavaFX в проект IntelliJ IDEA:

### Шаг 1: Скачивание JavaFX SDK
1. Перейдите на официальный сайт JavaFX: [https://gluonhq.com/products/javafx/](https://gluonhq.com/products/javafx/).
2. Скачайте подходящую версию JavaFX SDK для вашей операционной системы.
3. Разархивируйте скачанный архив в удобное место на вашем компьютере (например, `C:\javafx-sdk`).

---

### Шаг 2: Открытие настроек проекта в IntelliJ IDEA
1. Откройте проект в IntelliJ IDEA.
2. В верхнем меню выберите **File → Project Structure** (или нажмите `Ctrl + Alt + Shift + S`).

---

### Шаг 3: Добавление JavaFX в библиотеки проекта
1. В окне **Project Structure**:
   - Перейдите на вкладку **Libraries**.
   - Нажмите на кнопку **+** (Add).
   - Выберите **Java**.
2. В появившемся окне укажите путь к папке `lib` в скачанном вами JavaFX SDK.
   - Например: `C:\javafx-sdk\lib`.
   - Нажмите **OK**.
3. Убедитесь, что библиотека добавлена в модуль вашего проекта на вкладке **Modules** → выберите модуль проекта → вкладка **Dependencies**.

---

### Шаг 4: Настройка VM Options для запуска JavaFX
1. Откройте **Run → Edit Configurations**.
2. Выберите конфигурацию вашего приложения (например, `Main`).
3. В поле **VM options** добавьте следующий флаг (замените путь на тот, где вы распаковали JavaFX SDK):
   ```
   --module-path "C:\javafx-sdk\lib" --add-modules javafx.controls,javafx.fxml
   ```
4. Нажмите **OK** для сохранения настроек.

---

### Шаг 5: Проверка работы JavaFX
1. Убедитесь, что у вас есть простой код JavaFX для проверки, например:

   ```java
   import javafx.application.Application;
   import javafx.scene.Scene;
   import javafx.scene.control.Button;
   import javafx.scene.layout.StackPane;
   import javafx.stage.Stage;

   public class Main extends Application {
       @Override
       public void start(Stage primaryStage) {
           Button button = new Button("Click me!");
           StackPane root = new StackPane(button);

           Scene scene = new Scene(root, 300, 200);
           primaryStage.setTitle("JavaFX Test");
           primaryStage.setScene(scene);
           primaryStage.show();
       }

       public static void main(String[] args) {
           launch(args);
       }
   }
   ```

2. Запустите приложение. Если все сделано правильно, вы увидите окно JavaFX.

