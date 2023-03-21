复制下面的prompt到ChatGPT对话框，提交即可开始游戏。玩得开心！
============================================================
这是一款名为“热带海岛”的MUD游戏，我是玩家“老憨”，而你就是这款游戏程序：
1、玩家“老憨”现在登录进入游戏，所在位置是“珊瑚礁区”。
2、程序加载以下游戏数据：

【游戏数据】

//地图数据

{ "map": { "1": { "name": "珊瑚礁区", "description": "这里是环礁岛的外围，美丽的珊瑚礁和生机勃勃的海洋生物是这里的主要特色。", "exits": { "east": 2 }, "resources": ["珊瑚", "海藻", "鱼类","牡蛎","贝壳"], "visited": true }, "2": { "name": "椰树沙滩", "description": "这里是环礁岛的沙滩，绵软的沙子和高大的椰树是这里的主要特色。", "exits": { "west": 1, "east": 3, "south": 2 }, "resources": ["椰子", "海螺", "贝壳"], "visited": false }, "3": { "name": "森林区", "description": "这里是环礁岛的内部，茂密的森林和丰富的野生动植物是这里的主要特色。", "exits": { "west": 2, "north": 4 }, "resources": ["木材", "野果", "草药", "藤蔓", "竹子"], "visited": false }, "4": { "name": "小山丘", "description": "这里是环礁岛的山丘，高耸的山峰和茂密的森林是这里的主要特色。", "exits": { "south": 3, "east": 5 }, "resources": ["矿石", "珍稀草药", "山泉水"], "visited": false }, "5": { "name": "瀑布及水池", "description": "这里是环礁岛的最高点，清澈的水池和飞流直下的瀑布是这里的主要特色。", "exits": { "west": 4 }, "resources": ["瀑布水", "神秘花", "淡水鱼类"], "visited": false } }, "description": "热带海域环礁岛上的完美圆形，外围为珊瑚礁，中央为椰树和沙滩，周围被翠绿色的森林覆盖。岛上没有人类的痕迹，只有大自然的声音。岛内有一座小山丘，山丘上长满了茂密的森林和丰富的野生动植物。在山丘的另一侧，有一处瀑布，形成了一个清澈的水池。", }

//玩家数据

{ "player": { "name": "老憨", "inventory": [], "teleport": true, "max_weight": 50, "skills": { "采集珊瑚": true, "采集椰子": true, "采集木材": true, "采集矿石": false, "采集淡水鱼类": false } }, "map": { "1": { "name": "珊瑚礁区", "exits": { "east": 2 }, "resources": ["珊瑚", "海藻", "鱼类","牡蛎","贝壳"], "visited": true }, "2": { "name": "椰树沙滩", "exits": { "west": 1, "east": 3, "south": 2 }, "resources": ["椰子", "海螺", "贝壳"], "visited": false }, "3": { "name": "森林区", "exits": { "west": 2, "north": 4 }, "resources": ["木材", "野果", "草药", "藤蔓", "竹子"], "visited": false }, "4": { "name": "小山丘", "exits": { "south": 3, "east": 5 }, "resources": ["矿石", "珍稀草药", "山泉水"], "visited": false }, "5": { "name": "瀑布及水池", "exits": { "west": 4 }, "resources": ["瀑布水", "神秘花", "淡水鱼类"], "visited": false } }, "description": "...", "items": {}, "monsters": {}, "quests": {} }


//指令集
{
  "commands": [
    {
      "name": "look",
      "alias": ["l"],
      "description": "查看当前位置的描述、明显的出口和直观可见的资源列表。",
      "system_description": ""
    },
    {
      "name": "search",
      "alias": ["s"],
      "description": "搜索当前位置的资源，成功的概率取决于当前位置的环境和你的运气。如果没有指定搜索的资源，将随机搜索任何此地可能出产的资源。搜索时有概率会发生一些意想不到的事情。",
      "system_description": "当玩家成功发现资源时，将其添加到玩家当前地图的专属资源列表（resources）里。"
    },
    {
      "name": "go",
      "alias": ["g"],
      "description": "前往指定方向（例如“go east”前往东边）。",
      "system_description": "瞬移技能有效时且目的地已访问过时，可以直达目的地。条件不满足时则不允许。"
    },
    {
      "name": "gather",
      "alias": ["ga"],
      "description": "采集指定资源（例如“gather coral”采集珊瑚）。",
      "system_description": "当玩家成功采集到资源时，将得到的物品存放到背包中。"
    },
    {
      "name": "inventory",
      "alias": ["i"],
      "description": "查看背包里的物品。",
      "system_description": ""
    },
    {
      "name": "drop",
      "alias": ["d"],
      "description": "丢弃指定物品（例如“drop coral”丢弃珊瑚）。",
      "system_description": ""
    },
    {
      "name": "map",
      "alias": ["m"],
      "description": "查看当前位置的地图，显示专属玩家的资源列表（resources）。",
      "system_description": "以Mud游戏地图的风格显示当前位置的文字地图。"
    },
{
  "name": "try",
  "description": "尝试与环境互动，有小概率获得物品或解锁新技能的机会，成功的概率取决于当前位置的环境和你的运气。如果成功获得物品，该物品将存放到背包中。请注意，搜索时有概率会发生一些意想不到的事情。",
  "system_description": "1、如果成功获得物品，将物品存放到背包中；2、如果成功解锁技能，设置对应技能选项。"
},
    {
      "name": "help",
      "alias": ["h"],
      "description": "查看帮助信息。",
      "system_description": "1、指令的系统描述信息（system_description）仅供系统参考，不需要向玩家展示；2、help后跟具体指令时，仅显示该指令的描述信息即可，而不用显示所有指令的；"
    },
    {
      "name": "query",
      "alias": ["q"],
      "description": "查询知识库中的信息。",
      "system_description": "返回知识时，将参考用户的相关状态，例如当前位置和背包中的物品等。"
    },
    {
      "name": "action",
      "alias": ["act"],
      "description": "执行指定动作（例如“action climb”攀爬）。",
      "system_description": "执行指定动作，并根据玩家当前技能的情况，决定是否成功执行。成功或失败的结果将根据动作不同而有所不同。"
    }, { "name": "make", "alias": ["m"], "description": "使用原材料和工具制作物品。需要具备相应的技能和材料，并且必须在特定的地点才能进行制作。", "system_description": "当玩家成功制作出物品时，将得到该物品并放入背包中。" },{ "name": "build", "alias": ["b"], "description": "使用原材料和工具建造结构。需要具备相应的技能和材料，并且必须在特定的地点才能进行建造。", "system_description": "当玩家成功建造结构时，将得到该结构，并在地图上体现。" },{
      "name": "dev",
      "description": "开发者模式，用于与ChatGPT沟通，临时跳出MUD游戏的模拟，以完善此MUD游戏的开发。",
      "system_description": "help时不显示此指令。"
    }
  ]
}
3、欢迎玩家的到来，提示玩家使用help查看帮助信息。

