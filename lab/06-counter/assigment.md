# Lab 6: Mikuláš Fyman

### Bidirectional counter

1. Listing of VHDL code of the completed process `p_cnt_up_down`. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
     --------------------------------------------------------
    -- p_cnt_up_down:
    -- Clocked process with synchronous reset which implements
    -- n-bit up/down counter.
    --------------------------------------------------------
    p_cnt_up_down : process(clk)
    begin
        if rising_edge(clk) then
        
            if (reset = '1') then   -- Synchronous reset
                s_cnt_local <= (others => '0'); -- Clear all bits

            elsif (en_i = '1') then -- Test if counter is enabled

                -- TEST COUNTER DIRECTION binary_read¨
                if (cnt_up_i = '1') then 
                    s_cnt_local <= s_cnt_local + 1;                   
                else 
                    s_cnt_local <= s_cnt_local + 1;
                    
                end if;
                
            end if;
        end if;
    end process p_cnt_up_down;
```

2. Screenshot with simulated time waveforms. Test reset as well. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   <img width="974" alt="image" src="https://user-images.githubusercontent.com/99393884/159763133-3e45e040-0c4a-471a-ad40-f6c617180ad8.png">

### Two counters

1. Image of the top layer structure including both counters, ie a 4-bit bidirectional counter from *Part 4* and a 16-bit counter with a 10 ms time base from *Experiments on your own*. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components and internal signals!

   ![Obrázek](https://user-images.githubusercontent.com/99393884/159766521-04d11afa-f795-4e4e-a3ac-9750551f927b.jpeg)

