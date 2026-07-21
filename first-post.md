# Getting Started with Arduino TinyML

Placeholder intro paragraph — one or two sentences on what this post covers and why you wrote it. The loader grabs this file's first `#` heading as the post title, so keep it short and specific.

## Why TinyML on a microcontroller

A short paragraph explaining the motivation. You can use **bold text**, *italics*, and [links](https://example.com) freely — the loader's markdown renderer supports all of these.

## What you'll need

- An Arduino Nano 33 BLE Sense (or similar board with a built-in IMU)
- Arduino IDE with the TensorFlow Lite library installed
- A USB cable

## Steps

1. Collect sensor data and label it
2. Train a small model in Python
3. Convert the model to a `.h` file with `xxd`
4. Flash it to the board and run inference

## Code example

```cpp
void loop() {
  float x = readSensor();
  if (runInference(x) > 0.8) {
    Serial.println("Detected!");
  }
  delay(100);
}
```

## Result

A short closing paragraph on what happened, what you learned, or what's next. Replace this whole file with your real writing — the structure (one `#` title, `##` subheadings, code fences, lists) is all the loader needs.

## Tags

`arduino`, `tinyml`, `embedded`
