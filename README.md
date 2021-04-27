https://youtu.be/SXXOJV9HFtY

import pygame
import random 
from pygame.locals import *

WIDTH = 650
HEIGHT = 450
WIN = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Test Your Reaction Speed!")
background = pygame.image.load("background.jpg").convert()

FPS = 60
SIZE_WIDTH, SIZE_HEIGHT = 130,180
MONKEY = pygame.image.load("monkey.png")
MONKEY_SIT = pygame.transform.scale(MONKEY, (SIZE_WIDTH, SIZE_HEIGHT))
TIGER = pygame.image.load("tiger.png")
TIGER_ATTACK = pygame.transform.scale(TIGER, (SIZE_WIDTH, SIZE_HEIGHT))

def draw_window():
    WIN.blit(background, [0,0])
    pygame.display.flip()
    WIN.blit(MONKEY_SIT, (325,225))
    WIN.blit(TIGER_ATTACK, (100,200))
    pygame.display.update()


def main():

    clock = pygame.time.Clock()
    run = True
    clicking = False
    while run:
        clock.tick(FPS)
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                run = False     
        draw_window()
        
    for event in pygame.event.get():
        if event.type == pygame.MOUSEBUTTONDOWN:
          if event.button == 1:
             clicking  = True
    
    pygame.quit()

if __name__ == "__main__":
    main()

    
