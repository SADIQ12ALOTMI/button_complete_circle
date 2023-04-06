# button_complete_circle
![Screenshot_20230331_022951](https://user-images.githubusercontent.com/78486332/228987484-9a3ee372-8f9f-4f45-a9de-cf648c619010.png)
![Screenshot_20230331_022959](https://user-images.githubusercontent.com/78486332/228987501-cbfd868d-cd99-4254-9a29-2df6f960dbb1.png)
![Screenshot_20230331_023004](https://user-images.githubusercontent.com/78486332/228987503-5f7885f0-dc0b-4b7f-a094-eba1eebc9082.png)


# here code 
``` dart
//variable
  double _progress = 0.0;
  ```

# Widget Button_Progress_indictor
```  dart
CustomPaint(
                              size: const Size(80.0, 80.0),
                              painter: CircularProgressPainter(
                                progress: _progress,
                                color: kPrimaryColor,
                                strokeWidth: 4.0,
                              ),
                            ),

```
# class CircularProgressPainter 
``` dart
class CircularProgressPainter extends CustomPainter {
  final double progress;
  final Color color;
  final double strokeWidth;

  CircularProgressPainter({
    required this.progress,
    required this.color,
    required this.strokeWidth,
  });

  @override
  void paint(Canvas canvas, Size size) {
    final rect = Rect.fromCircle(
      center: Offset(size.width / 2, size.height / 2),
      radius: min(size.width, size.height) / 2,
    );
    final paint = Paint()
      ..style = PaintingStyle.stroke
      ..strokeWidth = strokeWidth
      ..color = color;
    canvas.drawArc(
      rect,
      -pi / 2,
      2 * pi * progress,
      false,
      paint,
    );
  }

  @override
  bool shouldRepaint(CustomPainter oldDelegate) => true;
}
```

