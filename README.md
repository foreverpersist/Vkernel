# Vkernel

## Motivation

> * 针对容器的隔离性需求,深入研究容器环境下操作系统内核的作用和定位,以及操作系统内核功能的解耦方法
> * 根据容器运行环境的隔离特征,研究操作系统虚拟化的层次化隔离模型
> * 根据云平台的具体需求,研究隔离性与资源利用率之间的权衡方法,在保障隔离性的前提下提升资源利用率

## Hierarchical Model

|-------------------------------------------
| ------------------                       |
| |  -------       |                       |
| |  | App |       |                       |
| |  -----------   |                       |
| |  | Vkernel |   |                       |
| |  -----------   |                       |
| |  Container     |                       |
| ------------------                       |
|------------------------------------------|
|   ----------    ----------------------   |
|   | Kernel |    | Cgroup | Namespace |   |
|   ----------    ----------------------   |
|------------------------------------------|
|               Hardware                   |
|------------------------------------------|

## Subsystem

> * 资源视图
> * 硬资源分配管理
> * 软资源分配管理
> * 硬件特性支持

## Code

### Intercept Syscall
|                        | In-kernel | UML | LD_PRELOAD | Modified-lib | ptrace |	
| :---:					 | :---:     | :-: | :---:      | :---:        | :---:  |
| Rapid Development      | *         | **  | ***        | **           | ***    |
| Powerful Prototypes    | ***       | **  | **         | **           | **     |
| Modularity             | *         | *   | **         | *            | ***    |
| Design Transferability | ***       | *** | *          | *            | **     |
| Runtime Compatibility  | ***       | *   | *          | *            | **     |
| Performance            | ***       | *   | * +        | * +          | *      |

