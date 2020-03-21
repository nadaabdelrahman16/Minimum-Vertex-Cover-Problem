using JuMP
using GLPK
model = Model(GLPK.Optimizer)
k=6
@variable(model, x[1:k],Bin)
@objective(model,Min,sum(x[1:k]))
@constraint(model,con1, x[1] + x[3] >= 1)
@constraint(model,con2, x[2] + x[4] >= 1)
@constraint(model,con3, x[3] + x[5] >= 1)
@constraint(model,con4, x[4] + x[5] >= 1)
@constraint(model,con5, x[5] + x[6] >= 1)
print(model)
optimize!(model)
println("RESULTS:")
println(" Minimum Vertex Cover result: $(objective_value(model))")
for i in 1:k
    println("X",i ,":  ", JuMP.value(x[i]))
end

println("optimal cover for the given graph is  ")
for i in 1:k
    if ( JuMP.value(x[i])==1)
    print("   ", "X",i ,"  , ")
    end
end





