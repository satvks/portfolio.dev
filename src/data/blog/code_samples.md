---
banner_alt: A Few Code Samples
banner: /blog/hello_world/digital-binary-code-landscape-banner.png
title_prefix: Introducing
title: Code Samples
description: A little more than a cheeky hello world a p5 program I learned about on youtube, and more to come.
date: '2024-09-12'
---

## A look at some code samples

---

### :milky_way: Flow Fields

- [p5.js](https://editor.p5js.org/satvks/sketches/LQNizmm_i)
    - Code Preview:
    ```javascript
        function Particle() {
            this.x = random(width);
            this.y = random(height);
            this.pos = createVector(this.x, this.y);
            this.vel = createVector(0, 0);
            this.acc = createVector(0, 0);
            this.r = 2.0;
            this.maxSpeed = 5;

            this.update = function () {
            this.pos.add(this.vel);
            this.vel.add(this.acc);
            this.acc.mult(0);
            this.vel.limit(this.maxSpeed);
        };
        this.applyForce = function (force) {
            this.acc.add(force);
        };
        this.follow = function (vectors) {
            // apply vectors to force
            var x = floor(this.pos.x / scl);
            var y = floor(this.pos.y / scl);
            var index = (x + y * xvec);
            var force = vectors[index];
            this.applyForce(force);
        };
     ```

### :camera: Frustum Culling in HLSL/C++
- Code Preview
```cpp
bool FrustumCamera::SphereVisible(const Point3D& center, float radius) const {
    // Determines whether a sphere is visible inside the five world-space frustum planes
    // calculated in UpdateNode() function.
    // The center coordinates passed to this function are already in world space.
    // This function should return false when a sphere is culled.
    float gp;
    for (int i = 0; i < 5; i++) {
        gp = Dot(worldFrustumPlane[i], center);
        if (gp <= -radius) {
            return false;
        }
    }
    return (true);
}

    bool FrustumCamera::BoxVisible(const Transform4D& transform, const Vector3D& size) const {
    // Determines whether a box is visible inside the five world-space 
    // frustum planes calculated in the UpdateNode() function.
    // This function should return false when a box is culled.
    // The size parameter contains the full length, width, and height of the box
    // along its object-space coordinate axes.
    
    // The transform parameter is the box's object-to-world transformation matrix.
    // Its first three columns correspond to the world-space directions of the box's x, y, and z axes.
    transform[i], where i = 0, 1, 2.
    transform.GetTranslation().

    // Calculate the center of the box in world space
    Vector3D hx, hy, hz;
    float rg, gp;
    hx = transform[0] * (size[0] / 2);
    hy = transform[1] * (size[1] / 2);
    hz = transform[2] * (size[2] / 2);
    Point3D center = transform.GetTranslation() + hx + hy + hz;

    // Check the box against each of the five frustum planes
    for (int i = 0; i < 5; i++) {
        // Calculate the radius of the box along the current frustum plane
        rg = fabsf(Dot(worldFrustumPlane[i], hx)) +
        fabsf(Dot(worldFrustumPlane[i], hy)) +
        fabsf(Dot(worldFrustumPlane[i], hz));

        // Calculate the dot product of the box's center and the current frustum plane
        gp = Dot(worldFrustumPlane[i], center);

        // If the box is behind the current frustum plane, return false
        if (gp <= -rg) {
            return false;
        }
    }

    // If the box is in front of all five frustum planes, return true
    return (true);
}
```
