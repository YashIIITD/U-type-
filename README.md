#U_TYPE INSTRUCTION SET
    elif data.split()[0] in U_Type:
        data = data.replace(",", " ")
        opcode = U_Type[data.split()[0]]["opcode"]
        decimal = int(data.split()[2])
        if decimal<0:
            bina = bin(abs(decimal))[2:].zfill(32) 
            bina = bina.replace("0", "X").replace("1", "0").replace("X", "1") 
            result = Two_complement(bina, "1")  
            imm = result 
            # print(imm)
        else :
            bina = bin(abs(decimal))[2:].zfill(32)
            imm = bina 
            # print(imm)

        output = imm[0:20] + Registers[data.split()[1]] + opcode
        binary_output.append(output)
        # print(output)
