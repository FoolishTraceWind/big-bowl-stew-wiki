# LWC 锁箱

## 锁箱子

**`/cpublic`** - _公共锁_

等价于 `/lwc -create public` 或 `/lwc -c public` 

任何人都可以访问, 但这可以防止别人锁你的箱子. 只有你可以去除这个锁.

**`/cprivate`** - _私有锁_

等价于 `/lock` , `/lwc -create private` 或 `/lwc -c private` 

没啥可以解释的——只有你能动这个箱子, 除非你授权给别人.

你可以给多个人授权, 在命令末尾加上人或用户组就可以. 如果在目标前加 `@` , ta 还可以修改这个锁的权限(但请放心, 你永远是箱子主人).

例子:

`/lock` - 给你自己的箱子上锁

`/cprivate Theergold g:bigBowl` - 给箱子上锁, 允许你自己, Theergold, 和用户组 `bigBowl` 打开.

`/lwc -c private @NaAlOH4` - 给箱子上锁, 并允许 NaAlOH4 修改哪些人可以打开箱子

**`/cpassword`** - _密码箱_

等价于 `/lwc -create password` 或 `/lwc -c password` 

每次登陆游戏后都需要输入密码来解锁, 任何知道密码的用户都可以打开这个箱子

例子:

`/cpassword 123456` - 用最笨的弱密码给箱子上锁(请不要这样)

**`/cdonation`** - _募捐箱_

等价于 `/lwc -create donation` 或 `/lwc -c donation` 

别人可以送给你东西, 但是没法拿走东西

**`/cdisplay`** - _透明箱_

等价于 `/lwc -create display` 或 `/lwc -c display` 

别人能看不能拿.

## 管理箱子锁

**`/cmodify`** - _修改箱子锁_

等价于 `/lwc -modify` 或 `/lwc -m` 

赋予命令中每个没有前缀的目标访问权限, 移除每个 `-` 前缀目标的访问权限, 给予每个 `@` 前缀目标管理权限.

目标可以是用户, group (格式为: `g:<group 名>` ) 或 town (格式为: `t:<town名>` ). 多个目标之间请加入空格.

例子:
`/lwc -m WooMai @bigBowl` - 允许 WooMai 打开箱子, 允许 bigBowl 组管理箱子锁.

`/cmodify -NaAlOH4` - 不再让 NaAlOH4 能打开箱子.

`/cmodify -g:smallBowl` - 不再让任何 smallBowl 组员能打开箱子

`/cmodify t:BowlTown` - 不再让任何 BowlTown 成员能打开箱子

**`/cremove`** - _解除一个箱子的锁_

等价于 `/unlock` , `/lwc -remove` 或 `/lwc -r` 

**`/cunlock`** - _使用密码解锁一个箱子_ 

等价于 `/lwc -unlock` 或 `/lwc -u` 

**`/cinfo`** - _检查箱子锁_

等价于 `/lwc -info` 或 `/lwc -i` 

**`/climits`** - _检查你上了多少个锁_

等价于 `/lwc -info limits` 或 `/lwc -i limits` 

## 配置

**`/credstone`** - _允许红石原件影响箱子_

等价于 `/lwc flag redstone` 

**`/cmagnet`** - _箱子(或容器)将自动吸取周围的物品_

等价于 `/lwc flag magnet` 

**`/cautoclose`** - _自动关闭打开数秒后的门_

等价于 `/lwc flag autoclose` 

**`/callowexplosions`** - _允许方块被炸毁_

等价于 `/lwc flag allowexplosions` 

**`/chopper`** - _控制与漏斗的交互_

注意: 这个功能会同时设置 `chopperin` 和 `chopperout` 

等价于 `/lwc flag hopper` 

** `/chopperin` / `/chopperout` ** - _允许漏斗输入/输出物品_

等价于 `/lwc flag hopperin` / `/lwc flag hopperout` 

## 模式

**炫迈模式** 允许你在多个箱子上连续执行最后输入的那个指令

**`/cpersist`** - _开启/关闭炫迈模式_

等价于 `/lwc mode persist` 

**掉落物转移模式** 让你的掉落物自动转移到指定箱子

**`/cdroptransfer`** 等价于 `/lwc mode droptransfer` 

**`/cdroptransfer select`** - _选择用于收集的箱子_

**`/cdroptransfer <on/off>`** - _模式开关_

**`/cdroptransfer status`** - _显示当前模式_

**无锁模式** 将不会在你放置箱子时上锁

**`/cnolock`** - _模式开关_

等价于 `/lwc mode nolock` 

**No spam 模式** 防止箱子锁向你发送消息

**`/nospam`** - _模式开关_

等价于 `/lwc mode nospam` 

## 其他

**`/lwc history <用户名>`** 搜索历史

**`/lwc details <history id>`** 显示特定 history id 对应的详细信息
