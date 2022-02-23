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
#### GreaterSoP = B1./A1 + /A1./A0.B0 + /A0.B1.B0 
##### '/' -> negation 


### *The K-map for the "less than" function*
|           |           |         |  **A1,A0**  |           |           |
| :-:       | :-:       | :-:     | :-:         | :-:       | :-:       | 
|           |           | ***0 0*** | ***0 1***     | ***1 1***   | ***1 0***   | 
|           | ***0 0***   | **0**   | 1           | 1         | 1         | 
| **B1,B0** |  ***0 1***  | **0**       | **0**       | 1         |  1        |
|           | ***1 1***   | **0**       | **0**            | **0**     | **0**          |
|           | ***1 0***   | **0**       | **0**            | 1         | **0**     |

#### Simplified PoS form of the "less than" function : 
#### LessPoS = (A1+A0).(/B1+/B2).(A1+/B1).(A1+/B0).(A0+/B1)
##### '/' -> negation 

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **xxxx??**

```vhdl
    p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case
        s_b <= "BCD_OF_YOUR_SECOND_LAST_ID_DIGIT"; -- Such as "0101" if ID = xxxx56
        s_a <= "BCD_OF_YOUR_LAST_ID_DIGIT";        -- Such as "0110" if ID = xxxx56
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = 'WRITE_CORRECT_VALUE_HERE') and
                (s_B_equals_A  = 'WRITE_CORRECT_VALUE_HERE') and
                (s_B_less_A    = 'WRITE_CORRECT_VALUE_HERE'))
        -- If false, then report an error
        report "Input combination COMPLETE_THIS_TEXT FAILED" severity error;

        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   ![your figure]()

3. Link to your public EDA Playground example:

   [https://www.edaplayground.com/...](https://www.edaplayground.com/...)

