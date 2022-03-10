## Preparation tasks (done before the lab at home)

1. Write characteristic equations and complete truth tables for D, JK, T flip-flops where `q(n)` represents main output value before the clock edge and `q(n+1)` represents value after the clock edge.

<img width="214" alt="image" src="https://user-images.githubusercontent.com/99393884/157645553-23bee69c-47bf-45fb-9ee6-f8e7743c9107.png">
<!--
\begin{align*}
    q_{n+1}^D =&~ \\
    q_{n+1}^{JK} =&\\
    q_{n+1}^T =&\\
\end{align*}
-->

   | **clk** | **d** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645652-80eef191-5e71-4b36-918c-a22baa4814d3.png"> | 0 | 0 | 0 | d = q(n+1) |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645665-fca57b9c-720c-489d-9ed3-35df90db49c7.png"> | 0 | 1 | 0 | d = q(n+1) |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645678-b30d16ae-17e2-4b26-b5ff-444d881b84a1.png"> | 1 | 0 | 1 | d = q(n+1) |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645693-c64194e2-b4d4-45d4-8628-68deda6945be.png"> | 1 | 1 | 1 | d = q(n+1) |

   | **clk** | **j** | **k** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-: | :-- |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645727-07247d4f-9a00-4546-9b58-6b9d5180dff6.png"> | 0 | 0 | 0 | 0 | No change |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645749-db70f0d6-183f-4238-a449-ea4211ad7f85.png"> | 0 | 0 | 1 | 1 | No change |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645772-ffa3e2ac-b81a-48de-b342-7524ec25bd2c.png"> | 0 | 1 | 0 | 0 | Reset |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645811-67a77149-7195-4e07-a6d8-e91090eb48ce.png"> | 0 | 1 | 1 | 0 | Reset |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645826-d10d29b5-04aa-4713-b0d3-101726a6b5f0.png"> | 1 | 0 | 0 | 1 | Set |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645835-0d980e51-a9f8-4470-a7f2-e1d23d85dda1.png"> | 1 | 0 | 1 | 1 | Set |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645845-da4b85be-cafc-4b6d-ad06-0f95d9103235.png"> | 1 | 1 | 0 | 1 | Toggle |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645861-821e7944-7297-4ba9-ac92-03e4ff3a0ea2.png"> | 1 | 1 | 1 | 0 | Toggle |

   | **clk** | **t** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645869-d9a741cf-a59f-494d-8ed0-41fc9933d372.png"> | 0 | 0 | 0 | No change |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645893-be205991-048e-453f-a971-5ef8ca0a1b37.png"> | 0 | 1 | 1 | No change |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157645904-d651e3ce-ea5b-440d-a101-8c0ddaaf7d3d.png"> | 1 | 0 | 1 | Toggle |
   | <img width="42" alt="image" src="https://user-images.githubusercontent.com/99393884/157646096-c414e100-e295-468e-a060-2352174d85d4.png"> | 1 | 1 | 0 | Toggle |

<!--
Dokreslit průběhy pro D-latch a D-type FF.

![Timing of seven-segment display](images/wavedrom_7-segment.png)

> The figure above was created in [WaveDrom](https://wavedrom.com/) digital timing diagram online tool. The figure source code is as follows:
>
```javascript
{
  signal:
  [
    ['Digit position',
      {name: 'Common anode: AN(3)', wave: 'xx01..01..01'},
      {name: 'AN(2)', wave: 'xx1'},
      {name: 'AN(1)', wave: 'xx1'},
      {name: 'AN(0)', wave: 'xx1'},
    ],
    ['Seven-segment data',
      {name: '4-digit value to display', wave: 'xx3333555599', data: ['3','1','4','2','3','1','4','2','3','1']},
      {name: 'Cathod A: CA', wave: 'xx01.0.1.0.1'},
      {name: 'CB', wave: 'xx0'},
      {name: 'CC', wave: 'xx0'},
      {name: 'CD', wave: 'xx0'},
      {name: 'CE', wave: 'xx1'},
      {name: 'CF', wave: 'xx1'},
      {name: 'CG', wave: 'xx0'},
    ],
    {name: 'Decimal point: DP', wave: 'xx01..01..01'},
  ],
  head:
  {
    text: '                    4ms   4ms   4ms   4ms   4ms   4ms   4ms   4ms   4ms   4ms',
  },
}
```
-->

<a name="part1"></a>

