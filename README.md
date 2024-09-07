def get_advanced_writer(file_name):
    def write_everything(*data_set):
        with open(file_name, 'w', encoding='utf-8') as file:
            for item in data_set:
                file.write(str(item) + '\n')
        return # выход из write_everything
    return write_everything

from random import choice
class MysticBall(object):
    def __init__(self, *words):
        self.words = words

    def __call__(self):
        return choice(self.words)

    def __len__(self):
        return len(self.words)

first_ball = MysticBall('Да', 'Нет', 'Наверное', 'да-да')
for i in range (0, 100): # сто случайных
    print(first_ball())

#print(first_ball.__len__())


print("Функциональное разнообразие")

first   = 'Мама мыла рамуоо'
second  = 'Рамена мало было'

check = list(map(lambda x, y: x == y, first, second))
#print(len(first), len(second))
print(check)


write = get_advanced_writer('example.txt')
write('Это строчка', ['А', 'это', 'уже', 'число', 5, 'в', 'списке'])


