module toggle_led(
    input clk,              
    input btnC,             
    output reg led          
);

    
    reg btn_prev_state;      

    initial begin
        led = 0;             
        btn_prev_state = 0;  
    end

    always @(posedge clk) begin
        
        if (btnC && !btn_prev_state) begin
           
            led <= ~led;
        end

        
        btn_prev_state <= btnC;
    end

endmodule
