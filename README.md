# hangman
def hangman(abc):
    wrong = 0
    image = ['',
             '______      ',
             '|    |      ',
             '|    0   く ',
             '|   <|>  る ',
             '|    |   し ',
             '|   //   い ',
             '|        ┆  ',
             '|           '
             ]
    moji = list(abc)
    ita = ['_'] * len(abc)
    win = False
    print('ようこそハングマンへ!')
    while wrong < len(image):
        print('\n')
        memo = '1文字を予想してね!間違いは8回までだよ!'
        memo1 = input(memo)
        if memo1 in moji:
            a = moji.index(memo1)
            ita[a] = memo1
            moji[a] = '$'
        else:
            wrong = wrong + 1
        print(' '.join(ita))
        e = wrong + 1
        print('\n'.join(image[0:e]))
        if '_' not in ita:
            print('貴方の勝利!')
            print(' '.join(ita))
            win = True
            break
    if not win:
        print('\n'.join(image))
        print('貴方の負け!答えは{}.'.format(abc))

print(hangman(random.choice(abc_list)))
