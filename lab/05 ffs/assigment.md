# Lab 5: Mikuláš Fyman

### Flip-flops

1. Listing of VHDL architecture for T-type flip-flop. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
architecture Behavioral of t_ff_rst is
    signal s_q : std_logic;
begin
    --------------------------------------------------------
    -- p_t_ff_rst:
    -- T type flip-flop with a high-active sync reset,
    -- rising-edge clk.
    -- q(n+1) = t./q(n) + /t.q(n)
    --------------------------------------------------------
    p_t_ff_rst : process(clk)
    begin
        if rising_edge(clk) then
             if (rst = '1') then
                s_q <= '0';
                q  <= '0';
                q_bar <= '1';
             else
                s_q <= (not(t) and s_q) or (t and not(s_q));
                q   <=  s_q;            
                q_bar <= not s_q;
                
          end if;
         end if;
    end process p_t_ff_rst;
end architecture Behavioral;
```

2. Screenshot with simulated time waveforms. Try to simulate both flip-flops in a single testbench with a maximum duration of 200 ns, including reset. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

  <img width="972" alt="image" src="https://user-images.githubusercontent.com/99393884/158629215-cfb5d48c-4ba1-4985-ac07-088d795f8815.png">

### Shift register

1. Image of the shift register `top` level schematic. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components and internal signals!

   ![image](https://user-images.githubusercontent.com/99393884/158628780-f50e0e88-914a-40d0-818e-f4f6487330c4.jpeg)
