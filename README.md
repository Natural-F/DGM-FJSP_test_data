Different file naming：
According to the combination of (E_ave, machine, job_insert), the folder is saved in the directory in the form of "M{machine}_E{E_ave}_I{job_insert}" and the data is written to "data.txt".

Data Description：

Line 1:

Meaning: Number of machines M_num

Type: int

Line 2:

Meaning: Total number of workpieces J_num

Type: int

Line 3:

Meaning: List of length J_num, each element represents the arrival time of the corresponding workpiece.

Type: list[int]

Line 4

Processing_time

Meaning: Processing time information. The length of the outer list is equal to J_num; for each workpiece, it is nested layer by layer according to the process.

Each process corresponds to a list of length M_num (if the process can be processed on a certain machine, a positive integer time is stored; if not, -1 is stored).

Type: list[list[list[int]]]

Structure diagram:

Processing_time[job_i] # The i-th workpiece
→ [op_1, op_2, ..., op_opNum_i] # List of each operation (op)
→ op_k = [t_0, t_1, ..., t_(M_num-1)] # -1 when not processable

Line 5:

Op_num

Meaning: List, length J_num, each element is the number of operations (Operation Number) contained in the corresponding workpiece.

Type: list[int]

Line 6:

Meaning: Mapping relationship between workpiece number and its operation number. The key is the workpiece index (starting from 0), and the value is the operation number of the workpiece.

Type: dict[int, int]

Line 7:

Power_active

Meaning: Processing power information corresponding to the Processing_time structure.

It also consists of three layers of "workpiece → process → machine". When processing is not possible, -1 is stored.

Type: list[list[list[int]]]

The structure is the same as Processing_time, but it stores power values.

Line 8:

Power_idle

Meaning: Idle power list, indicating the power consumption of each machine when idle.

Type: list[int]

Length: M_num

<!--
第 1 行：
含义：机器数量 M_num
类型：int

第 2 行：
含义：工件总数J_num
类型：int

第 3 行：
含义：长度为J_num的列表，每个元素表示相应工件的到达时刻 (Arrival Time)。
类型：list[int]

第 4 行
Processing_time
含义：加工时间信息。外层列表长度等于J_num；对每个工件，再按工序逐层嵌套。
每个工序对应一个长度为M_num的列表(若该工序能在某台机器加工，存储一个正整数时间；若不能则存 -1)。
类型：list[list[list[int]]]

结构示意：
Processing_time[job_i] # 第 i 个工件
→ [op_1, op_2, ..., op_opNum_i] # 每个操作(op)构成的 list
→ op_k = [t_0, t_1, ..., t_(M_num-1)] # 不可加工时为 -1


第 5 行：
Op_num
含义：列表，长度为 J_num，每个元素是对应工件包含的操作次数 (Operation Number)。
类型：list[int]

第 6 行：
含义：工件编号到其操作数的映射关系。键为工件下标(从 0 开始)，值为该工件的操作数。
类型：dict[int, int]


第 7 行：
Power_active
含义：与 Processing_time 结构对应的加工功率信息。
同样由“工件 → 工序 → 机器”三层嵌套组成。不可加工时存 -1。
类型：list[list[list[int]]]
结构与 Processing_time 相同、但存储功率值。


第 8 行：
Power_idle
含义：空闲功率列表，表示各机器处于空闲时的功率消耗。
类型：list[int]
长度：M_num
-->
