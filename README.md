# Yoo
Plen sim
import pygame
import sys

# Initialize Pygame
pygame.init()

# Set up the screen
width, height = 800, 600
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Control the Plane")

# Colors
sky_blue = (135, 206, 235)
white = (255, 255, 255)
black = (0, 0, 0)

# Plane variables
plane_image = pygame.image.load("plane.png")  # Replace "plane.png" with your plane image file
plane_rect = plane_image.get_rect()
plane_rect.center = (width // 2, height // 2)
plane_speed = 500

# Main game loop
running = True
while running:
    screen.fill(sky_blue)

    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    keys = pygame.key.get_pressed()
    if keys[pygame.K_UP]:
        plane_rect.y -= plane_speed
    if keys[pygame.K_DOWN]:
        plane_rect.y += plane_speed
    if keys[pygame.K_LEFT]:
        plane_rect.x -= plane_speed
    if keys[pygame.K_RIGHT]:
        plane_rect.x += plane_speed

    screen.blit(plane_image, plane_rect)

    pygame.display.flip()

pygame.quit()
sys.exit()
