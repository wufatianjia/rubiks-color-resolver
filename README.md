# rubiks-color-resolver

## python3 install
```
$ sudo python3 -m pip install git+https://github.com/dwalton76/rubiks-color-resolver.git
```

## micropython install

First [install micropython](https://github.com/micropython/micropython/wiki/Getting-Started) then:
```
$ git clone https://github.com/dwalton76/rubiks-color-resolver.git
$ cd rubiks-color-resolver
$ sudo make install
```

## Overview
rubiks-color-resolver.py and rubiks-color-resolver-micropython.py
- accepts a JSON string of RGB values for each square of a rubik'ss cube. 2x2x2, 3x3x3, 4x4x4, 5x5x5, 6x6x6 and 7x7x7 are supported.
- analyzes all RGB values to assign each square one of the six colors of the cube. It then uses a Travelling Salesman algorithm (tsp_solver) to sort the colors.

In the following example the RGB values for square 1 is (39, 71, 43).  In this particular example the RGB values were collected via the Lego Mindstorms EV3 color sensor. The cube state for this cube is LUFLUBLBRBLFBFFLBDRFLUURLUUUFDFDRLRURFLBRFLBUDUDRLRRBBBBFFFLLLRBDBUUUDDDUDDBDDDFUULBFRRFLRRBRDDF.
```
dwalton@laptop ~/l/rubiks-color-resolver> rubiks-color-resolver.py --rgb '{"58": [202, 208, 224], "34": [250, 18, 6], "9": [112, 4, 4], "79": [197, 230, 79], "13": [30, 95, 187], "51": [104, 4, 2], "39": [246, 11, 8], "70": [122, 4, 0], "48": [203, 230, 65], "63": [37, 165, 78], "32": [36, 167, 73], "25": [209, 215, 231], "16": [255, 24, 4], "67": [234, 12, 7], "55": [189, 195, 211], "49": [32, 98, 185], "29": [221, 237, 79], "74": [125, 6, 2], "7": [253, 10, 2], "76": [13, 84, 164], "72": [27, 146, 66], "45": [212, 218, 234], "80": [45, 161, 88], "57": [255, 16, 5], "35": [103, 3, 1], "73": [255, 26, 3], "90": [41, 173, 74], "18": [24, 86, 173], "20": [152, 159, 177], "60": [186, 189, 206], "14": [49, 181, 95], "1": [220, 12, 8], "6": [21, 85, 172], "66": [181, 195, 222], "89": [36, 159, 69], "43": [253, 10, 2], "5": [168, 173, 192], "81": [89, 4, 0], "8": [21, 87, 174], "42": [39, 178, 95], "11": [255, 12, 5], "37": [130, 5, 3], "15": [47, 181, 94], "91": [38, 174, 74], "95": [130, 5, 3], "87": [20, 86, 172], "78": [205, 235, 89], "54": [201, 207, 223], "2": [172, 177, 197], "22": [206, 235, 57], "17": [211, 236, 83], "56": [104, 4, 2], "46": [211, 235, 87], "69": [43, 181, 103], "64": [210, 230, 44], "10": [24, 93, 188], "88": [21, 87, 173], "19": [171, 176, 196], "92": [255, 12, 4], "33": [127, 5, 2], "77": [130, 5, 3], "36": [154, 163, 192], "59": [196, 202, 218], "31": [202, 230, 58], "30": [207, 235, 65], "75": [118, 5, 1], "44": [18, 82, 172], "24": [182, 210, 40], "53": [255, 20, 2], "4": [250, 11, 6], "94": [255, 17, 6], "96": [31, 98, 177], "50": [195, 224, 46], "62": [211, 234, 64], "52": [32, 135, 66], "26": [210, 238, 58], "93": [254, 19, 2], "82": [240, 9, 1], "84": [120, 5, 0], "85": [18, 72, 144], "83": [108, 5, 0], "28": [16, 78, 165], "86": [25, 86, 169], "21": [207, 213, 229], "41": [130, 5, 3], "40": [17, 74, 163], "12": [41, 174, 85], "71": [113, 5, 3], "3": [31, 153, 70], "27": [201, 230, 50], "38": [36, 173, 91], "68": [11, 66, 149], "65": [193, 208, 231], "47": [186, 201, 222], "61": [56, 179, 88], "23": [195, 224, 44]}'

[snip]
LUFLUBLBRBLFBFFLBDRFLUURLUUUFDFDRLRURFLBRFLBUDUDRLRRBBBBFFFLLLRBDBUUUDDDUDDBDDDFUULBFRRFLRRBRDDF
dwalton@laptop ~/l/rubiks-color-resolver>
```
