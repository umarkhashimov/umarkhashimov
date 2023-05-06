
![Banner](./banner.jpg)
<h1>Hello my name is Umar !</h1>
<!-- sample html code  -->
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mouse Line</title>
    <style>
        body {
            background-color: black;
            margin: 0;
            padding: 0;
            overflow: hidden;
        }

        div {
            position: absolute;
            width: 50px;
            height: 50px;
            background-color: red;
            border: 1px dotted rgba(0, 0, 0, 0.1);
            border-radius: 50%;
            animation: disapear 1s 0.4s;
            box-shadow: 0 0 10px red;
        }

        @keyframes disapear {
            0% {
                background-color: orangered;
                box-shadow: 0 0 10px orangered;
            }

            40% {
                background-color: orange;
                box-shadow: 0 0 15px orange;
            }

            80% {
                background-color: yellow;
                box-shadow: 0 0 25px yellow;
            }

            100% {
                width: 10px;
                height: 10px;
            }
        }
    </style>
</head>

<body>

    <script>

        function Circles(id, pTop, pLeft) {
            let created = document.createElement('div')
            created.setAttribute('number', id)
            created.style.top = pTop - 25 + 'px'
            created.style.left = pLeft - 25 + 'px'

            let animate = function () {
                created.animate([
                    { top: `${pTop - 25}px`, left: `${pLeft - 25}px` },
                    { top: `${pTop}px`, left: `${pLeft}px` }
                ], { duration: 1000, iterations: 1, delay: 350 })
            };

            let deleteDiv = function () {
                setTimeout(function () {
                    created.remove()
                }, 1000)
            };

            this.draw = function () {
                document.body.append(created)
                animate()
                deleteDiv()
            }
        }


        let amount = 0
        document.onmousemove = (event) => {
            amount++
            let d = new Circles(amount, event.clientY, event.clientX)
            d.draw()
        }

    </script>
</body>
<!-- retro visitor counter -->
<p align="center"> 
  <img src="https://profile-counter.glitch.me/Master2907/count.svg" />
</p>