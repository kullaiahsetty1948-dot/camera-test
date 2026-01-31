# camera-test
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>👀</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: #000;
      color: #fff;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
    }
    button {
      padding: 14px 24px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background: white;
      color: black;
    }
    video {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  </style>
</head>
<body>

<div id="screen">
  <h2>Ready to see my fine shii? 😌</h2>
  <br>
  <button onclick="openCam()">Yeah 👀</button>
</div>

<script>
  async function openCam() {
    try {
      const stream = await navigator.mediaDevices.getUserMedia({
        video: { facingMode: "user" }
      });

      document.body.innerHTML = "<video autoplay playsinline></video>";
      const video = document.querySelector("video");
      video.srcObject = stream;
    } catch (e) {
      alert("Camera permission needed 😉");
    }
  }
</script>

</body>
</html>
