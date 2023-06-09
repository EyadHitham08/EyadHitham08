- 👋 Hi, I’m @EyadHitham08
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
EyadHitham08/EyadHitham08 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->```python

import pygame

import random

# initialize pygame

pygame.init()

# create a screen with width=600 and height=600

screen = pygame.display.set_mode((600, 600))

# set the title and icon

pygame.display.set_caption("Fishing Game")

icon = pygame.image.load("icon.png")

pygame.display.set_icon(icon)

# create a background

background = pygame.Surface(screen.get_size())

background.fill((0, 0, 255))

# create a fish

fish = pygame.image.load("fish.png")

fish_x = random.randint(0, 550)

fish_y = random.randint(0, 550)

fish_dx = random.choice([-1, 1])

fish_dy = random.choice([-1, 1])

# create a fishing rod

rod = pygame.image.load("rod.png")

rod_x = 300

rod_y = 0

# create a hook

hook = pygame.image.load("hook.png")

hook_x = rod_x + 25

hook_y = rod_y + 100

# create a score

score = 0

font = pygame.font.SysFont("arial", 32)

# create a game loop

running = True

while running:

    # draw the background on the screen

    screen.blit(background, (0, 0))

    # draw the fish on the screen

    screen.blit(fish, (fish_x, fish_y))

    # draw the rod on the screen

    screen.blit(rod, (rod_x, rod_y))

    # draw the hook on the screen

    screen.blit(hook, (hook_x, hook_y))

    # draw the score on the screen

    text = font.render("Score: " + str(score), True, (255, 255, 255))

    screen.blit(text, (10, 10))

    # update the display

    pygame.display.update()

    # check for events

    for event in pygame.event.get():

        # if the user clicks the close button, exit the game loop

        if event.type == pygame.QUIT:

            running = False

        # if the user moves the mouse, update the rod and hook positions

        if event.type == pygame.MOUSEMOTION:

            mouse_x, mouse_y = event.pos

            rod_x = mouse_x - 25

            hook_x = rod_x + 25

    # move the fish randomly

    fish_x += fish_dx

    fish_y += fish_dy

    # check for collisions with the edges of the screen

    if fish_x < 0 or fish_x > 550:

        fish_dx *= -1

    if fish_y < 0 or fish_y > 550:

        fish_dy *= -1

    # check for collisions with the hook

    if abs(fish_x - hook_x) < 50 and abs(fish_y - hook_y) < 50:

        # increase the score by one

        score += 1
![—Pngtree—school kids_3691486](https://github.com/EyadHitham08/EyadHitham08/assets/136049109/53df93f3-f5a4-4ce7-9ee5-4d85d73e3b94)


        # reset the fish position and direction

        fish_x = random.randint(0, 550)

        fish_y = random.randint(0, 550)

        fish_dx = random.choice([-1, 1])

        fish_dy = random.choice([-1, 1])

```
