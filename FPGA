module jk_flipflop (
    input wire clk,
    input wire j,
    input wire k,
    output reg q,
    output reg h
);

always @(posedge clk) begin
    if (j && k) begin
        // Toggle q and h when both J and K are 1
        q <= ~q;
        h <= ~h;
    end else if (j) begin
        // Set q to 1 when J is 1
        q <= 1;
        h <= 0;
    end else if (k) begin
        // Set q to 0 when K is 1
        q <= 0;
        h <= 1;
    end
    // If both J and K are 0, do nothing
end

endmodule
