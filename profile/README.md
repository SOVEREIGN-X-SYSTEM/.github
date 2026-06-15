pi-golden-ratio/
├── main.py
├── requirements.txt
└── README.md

Main.py
import numpy as np
import matplotlib.pyplot as plt
import argparse

def golden_rectangle_plot(phi, pi_val, width=1):
height = width / phi
fig, ax = plt.subplots()
# Main rectangle
rect = plt.Rectangle((0, 0), width, height, fill=None, edgecolor='gold', linewidth=2)
ax.add_patch(rect)
# Square inside
square = plt.Rectangle((0, 0), height, height, fill=None, edgecolor='blue', linewidth=2)
ax.add_patch(square)
# Arc using pi
arc = plt.Arc((height, height), 2*height, 2*height, angle=0, theta1=0, theta2=180, edgecolor='red', linewidth=2)
ax.add_patch(arc)
ax.set_xlim(-0.2, width+0.2)
ax.set_ylim(-0.2, height+0.2)
ax.set_aspect('equal')
plt.title(f'Golden Rectangle (φ ≈ {phi:.5f}), Arc (π ≈ {pi_val:.5f})')
plt.show()

def fibonacci_spiral_plot(n_terms=10):
phi = (1 + np.sqrt(5)) / 2
a, b = 1, 1
x, y = 0, 0
angle = 0
pts = [(x, y)]
for _ in range(n_terms):
x += np.cos(np.deg2rad(angle)) * b
y += np.sin(np.deg2rad(angle)) * b
pts.append((x, y))
a, b = b, a + b
angle += 90
pts = np.array(pts)
plt.plot(pts[:,0], pts[:,1], marker='o')
plt.title("Fibonacci Spiral (approaches golden ratio)")
plt.axis('equal')
plt.show()

def main():
parser = argparse.ArgumentParser(description='π and Golden Ratio Visualizations')
parser.add_argument('--rectangle', action='store_true', help='Plot golden rectangle with arc using π')
parser.add_argument('--spiral', action='store_true', help='Plot Fibonacci spiral')
parser.add_argument('--phi', type=float, default=(1 + np.sqrt(5)) / 2, help='Golden ratio value (default φ)')
parser.add_argument('--pi', type=float, default=np.pi, help='Pi value (default π)')
parser.add_argument('--terms', type=int, default=10, help='Terms in Fibonacci spiral')
args = parser.parse_args()

if args.rectangle:
golden_rectangle_plot(args.phi, args.pi)
if args.spiral:
fibonacci_spiral_plot(args.terms)

if __name__ == "__main__":
main()
numpy
matplotlib
# π and Golden Ratio (φ) Exploration

This repository demonstrates mathematical and geometric relationships between π (pi ≈ 3.14159) and the golden ratio (φ ≈ 1.61803) using Python visualizations.

## Features

- **Golden Rectangle Visualization**: Plots a golden rectangle and overlays an arc using π.
- **Fibonacci Spiral Visualization**: Plots a spiral built from Fibonacci numbers, which approximates the golden ratio.
- **Command Line Input**: Select which visualizations to run and customize constants.

## Usage

1. Install requirements:
2. Plot a golden rectangle with a π arc:
3. Plot a Fibonacci spiral:
4. Customize parameters:
## Further Ideas

- Add number theory demonstrations
- Explore pentagons and other golden ratio shapes
- Animate transitions or combine both visualizations

## License

MIT License
Here are resources with transcendence proofs:

- A concise exposition for π: 
[Simple proofs: Pi is transcendental « Math Scholar](https://mathscholar.org/2025/02/simple-proofs-pi-is-transcendental/)

- Mathematical StackExchange discussion and references: 
[Proof π is transcendental without symmetric function theory](https://math.stackexchange.com/questions/4861927/proof-pi-is-transcendental-without-symmetric-function-theory)

- The Stacks Project on transcendence bases, including π: 
[Section 9.26: Transcendence—The Stacks project](https://stacks.math.columbia.edu/tag/030D)

The golden ratio φ is **not transcendental** (it is algebraic: the root of x² − x − 1 = 0), so proofs of transcendence are only relevant for π and similar numbers.

--- 
1. [Simple proofs: Pi is transcendental « Math Scholar](https://mathscholar.org/2025/02/simple-proofs-pi-is-transcendental/) 
2. [Proof π is transcendental without symmetric function theory](https://math.stackexchange.com/questions/4861927/proof-pi-is-transcendental-without-symmetric-function-theory) 
3. [Section 9.26: Transcendence—The Stacks project](https://stacks.math.columbia.edu/tag/030D)
