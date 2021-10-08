```swift
    private func animateRing() {
        let circularPath = UIBezierPath(
            arcCenter: view.center,
            radius: 120,
            startAngle: -CGFloat.pi / 2,
            endAngle: 2 * CGFloat.pi,
            clockwise: true
        )

        let trackShapeLayer = CAShapeLayer()
        trackShapeLayer.path = circularPath.cgPath
        trackShapeLayer.strokeColor = UIColor.quizletYellow.withAlphaComponent(0.3).cgColor
        trackShapeLayer.lineWidth = 15
        trackShapeLayer.fillColor = UIColor.clear.cgColor
        view.layer.addSublayer(trackShapeLayer)

        let shapeLayer = CAShapeLayer()
        shapeLayer.path = circularPath.cgPath
        shapeLayer.strokeColor = UIColor.quizletYellow.cgColor
        shapeLayer.lineWidth = 15
        shapeLayer.fillColor = UIColor.clear.cgColor
        shapeLayer.strokeEnd = 0
        shapeLayer.lineCap = CAShapeLayerLineCap.round
        view.layer.addSublayer(shapeLayer)

        let basicAnimation = CABasicAnimation(keyPath: "strokeEnd")
        basicAnimation.toValue = 1
        basicAnimation.duration = CFTimeInterval(3)
        basicAnimation.fillMode = CAMediaTimingFillMode.forwards
        basicAnimation.isRemovedOnCompletion = false
        shapeLayer.add(basicAnimation, forKey: "someBasicString")
    }

```