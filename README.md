# load-point
loading
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8" />
    <title>Square Lighting Sides</title>
    <style>
        body {
            background: #000;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .square {
            position: relative;
            width: 200px;
            height: 200px;
        }
        .light {
            position: absolute;
            background: #39ff14;
            box-shadow: 0 0 20px 5px #39ff14;
            transition: all 4s;
        }
    </style>
</head>
<body>
    <div class="square">
        <div class="light"></div>
    </div>
    <script>
        const light = document.querySelector('.light');
        const sides = [
            { top: 0, left: 0, width: '100%', height: '10px', borderRadius: '10px 10px 0 0' }, // top
            { top: 0, left: 'calc(100% - 10px)', width: '10px', height: '100%', borderRadius: '0 10px 10px 0' }, // right
            { top: 'calc(100% - 10px)', left: 0, width: '100%', height: '10px', borderRadius: '0 0 10px 10px' }, // bottom
            { top: 0, left: 0, width: '10px', height: '100%', borderRadius: '10px 0 0 10px' } // left
        ];
        let current = 0;
        function animateLight() {
            const side = sides[current];
            light.style.top = side.top;
            light.style.left = side.left;
            light.style.width = side.width;
            light.style.height = side.height;
            light.style.borderRadius = side.borderRadius;
            current = (current + 1) % sides.length;
        }
        setInterval(animateLight, 4000);
        animateLight();
    </script>
</body>
</html>
