import random
import copy

class Hat:
    def __init__(self, **balls):
        self.contents = []
        for color, count in balls.items():
            self.contents.extend([color] * count)

    def draw(self, number):
        number = min(number, len(self.contents))
        return [self.contents.pop(random.randrange(len(self.contents))) for _ in range(number)]

def experiment(hat, expected_balls, num_balls_drawn, num_experiments):
    matches = 0

    for _ in range(num_experiments):
        experiment_hat = copy.deepcopy(hat)
        balls_drawn = experiment_hat.draw(num_balls_drawn)
        if all(balls_drawn.count(color) >= count for color, count in expected_balls.items()):
            matches += 1

    return matches / num_experiments
