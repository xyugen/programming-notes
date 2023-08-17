## JavaFX Basics

```java
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class MyApp extends Application {
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        primaryStage.setTitle("JavaFX App");
        Button button = new Button("Click Me!");
        StackPane layout = new StackPane();
        layout.getChildren().add(button);
        Scene scene = new Scene(layout, 300, 250);
        primaryStage.setScene(scene);
        primaryStage.show();
    }
}
```

## UI Components

```java
import javafx.scene.control.Label;
import javafx.scene.control.TextField;
import javafx.scene.control.Button;
import javafx.scene.layout.VBox;

Label label = new Label("Enter your name:");
TextField textField = new TextField();
Button button = new Button("Submit");
VBox layout = new VBox(10);
layout.getChildren().addAll(label, textField, button);
```

## Event Handling

```java
button.setOnAction(e -> {
    String input = textField.getText();
    System.out.println("Hello, " + input + "!");
});
```

## Scene Switching

```java
Stage primaryStage = new Stage();
Scene scene1 = new Scene(layout1, 400, 300);
Scene scene2 = new Scene(layout2, 400, 300);

primaryStage.setScene(scene1);

button.setOnAction(e -> primaryStage.setScene(scene2));
```

## Styles and CSS

```java
scene.getStylesheets().add("styles.css");

// In styles.css
.button {
    -fx-font-size: 14pt;
    -fx-background-color: #007ACC;
    -fx-text-fill: white;
}
```

## UI Controls

```java
import javafx.scene.control.ComboBox;
import javafx.scene.control.ListView;
import javafx.scene.control.CheckBox;
import javafx.scene.control.RadioButton;
import javafx.scene.control.ToggleGroup;

ComboBox<String> comboBox = new ComboBox<>();
ListView<String> listView = new ListView<>();
CheckBox checkBox = new CheckBox("Check me");
RadioButton radioButton1 = new RadioButton("Option 1");
RadioButton radioButton2 = new RadioButton("Option 2");
ToggleGroup group = new ToggleGroup();
radioButton1.setToggleGroup(group);
radioButton2.setToggleGroup(group);
```

## Layout Management

```java
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.HBox;
import javafx.scene.layout.VBox;
import javafx.scene.layout.GridPane;

BorderPane borderPane = new BorderPane();
HBox hbox = new HBox();
VBox vbox = new VBox();
GridPane gridPane = new GridPane();
```

## Drawing and Graphics

```java
import javafx.scene.canvas.Canvas;
import javafx.scene.canvas.GraphicsContext;

Canvas canvas = new Canvas(400, 300);
GraphicsContext gc = canvas.getGraphicsContext2D();

gc.setFill(Color.GREEN);
gc.fillRect(50, 50, 100, 100);
```

## Charts and Data Visualization

```java
import javafx.scene.chart.LineChart;
import javafx.scene.chart.NumberAxis;
import javafx.scene.chart.XYChart;

NumberAxis xAxis = new NumberAxis();
NumberAxis yAxis = new NumberAxis();
LineChart<Number, Number> lineChart = new LineChart<>(xAxis, yAxis);

XYChart.Series<Number, Number> series = new XYChart.Series<>();
series.getData().add(new XYChart.Data<>(1, 10));
lineChart.getData().add(series);
```

## WebView for Web Content

```java
import javafx.scene.web.WebView;

WebView webView = new WebView();
webView.getEngine().load("https://www.example.com");
```

>[!Note]
>This JavaFX cheat-sheet provides you with key concepts and examples to get started with JavaFX programming.
