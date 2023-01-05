## [Two fighters, one winner.](https://www.codewars.com/kata/577bd8d4ae2807c64b00045b)

- Create a function that returns the name of the winner in a fight between two fighters.

- Each fighter takes turns attacking the other and whoever kills the other first is victorious. Death is defined as having health <= 0.

- Each fighter will be a Fighter object/instance. See the Fighter class below in your chosen language.

- Both health and damagePerAttack (damage_per_attack for python) will be integers larger than 0. You can mutate the Fighter objects.

- Your function also receives a third argument, a string, with the name of the fighter that attacks first.

```python
declare_winner(Fighter("Lew", 10, 2), Fighter("Harry", 5, 4), "Lew") => "Lew"
  
  Lew attacks Harry; Harry now has 3 health.
  Harry attacks Lew; Lew now has 6 health.
  Lew attacks Harry; Harry now has 1 health.
  Harry attacks Lew; Lew now has 2 health.
  Lew attacks Harry: Harry now has -1 health and is dead. Lew wins.
```
```python
class Fighter(object):
    def __init__(self, name, health, damage_per_attack):
        self.name = name
        self.health = health
        self.damage_per_attack = damage_per_attack
        
    def __str__(self): return "Fighter({}, {}, {})".format(self.name, self.health, self.damage_per_attack)
    __repr__=__str__
```
 

Solution:

```python
def declare_winner(fighter1, fighter2, first_attacker):
    fighterOneLives = math.ceil(fighter1.health/fighter2.damage_per_attack)
    fighterTwoLives = math.ceil(fighter2.health/fighter1.damage_per_attack)
    if fighterOneLives == fighterTwoLives:
        return first_attacker
    else:
        return fighter1.name if fighterOneLives > fighterTwoLives else fighter2.name

print(declare_winner(Fighter("Lew", 10, 2),Fighter("Harry", 5, 4), "Lew")) # Lew
print(declare_winner(Fighter("Harald", 20, 5), Fighter("Harry", 5, 4), "Harry")) # Harald
```