# Lab 2: Mikuláš Fyman

### 2-bit comparator

## ***Karnaugh maps for other two functions:***

### *The K-map for the "graeter than" function*
|           |           |         |  **A1,A0**  |           |           |
| :-:       | :-:       | :-:     | :-:         | :-:       | :-:       | 
|           |           | ***0 0*** | ***0 1***     | ***1 1***   | ***1 0***   | 
|           | ***0 0***   | 0   | 0           | 0         | 0         | 
| **B1,B0** |  ***0 1***  | **1**        | 0       | 0         |  0        |
|           | ***1 1***   | **1**        | **1**            | 0    | **1**         |
|           | ***1 0***   | **1**        | **1**            | 0         | 0     |

#### Simplified SoP form of the "greater than" function : 
#### GreaterSoP = B1 * notA1 + notA1 * notA0 * B0 + notA0 * B1 * B0
 


### *The K-map for the "less than" function*
|           |           |         |  **A1,A0**  |           |           |
| :-:       | :-:       | :-:     | :-:         | :-:       | :-:       | 
|           |           | ***0 0*** | ***0 1***     | ***1 1***   | ***1 0***   | 
|           | ***0 0***   | **0**   | 1           | 1         | 1         | 
| **B1,B0** |  ***0 1***  | **0**       | **0**       | 1         |  1        |
|           | ***1 1***   | **0**       | **0**            | **0**     | **0**          |
|           | ***1 0***   | **0**       | **0**            | 1         | **0**     |

#### Simplified PoS form of the "less than" function : 
#### LessPoS = (A1 + A0) * (notB1 + notB0) * (A1 + notB1) * (A1 + notB0) * (A0 + notB1)


### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **230246**

```vhdl
   p_stimulus : process
    
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case
        s_b <= "0100"; -- Such as "0100" if ID = xxxx46
        s_a <= "0110";        -- Such as "0110" if ID = xxxx46
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Test failed for input combination: 0100, 0110" severity 			error;

        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait;
    
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   <img width="1199" alt="image" src="https://user-images.githubusercontent.com/99393884/155323884-34db3178-2044-4d10-a62c-60d227eecd62.png">


3. Link to your public EDA Playground example:

   [https://www.edaplayground.com/x/jC9N]

