# Denim-care
Ray of light


![buh](https://github.com/nicolasbaez/Denim-care/blob/main/xp026.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
n = 90;
k = 0;
draw = (_) => {
  clear();
  for (i = -n + k; i < n + k; i += 0.25) {
    noFill();
    stroke(255, 64, map(i, -n, n, 255, 0), noise(i) * 255);
    beginShape();
    for (j = k; j < 6 + k; j += 0.1) {
      r = n;
      vertex(r * noise(j, i, k) * cos(j), r * noise(i, j, k) * sin(j), i * n);
    }
    endShape();
  }
  k -= 0.03;
};
keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp026.gif", 300, { delay: 0, units: "frames" });
  }
};
