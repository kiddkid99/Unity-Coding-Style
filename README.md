# C# 程式碼撰寫風格

## 規則定義
1. PascalCase - 每個單字的首字都為大寫，範例: Player, PlayerController
2. camelCase - 只有第一個單字的首字為小寫，範例: player, playerController

## 格式規範

### 命名規則

1. Private & protected field - 底線 + camelCase。範例: _speed, _moveSpeed 
2. Public field - PascelCase
3. Property - PascelCase
4. Const - 全大寫，多個單字間用底線隔開。範例: SPEED, MAX_SPEED
5. Namespace - PascalCase
6. Class - PascalCase
7. Enum & Enum Value - PascalCase
8.  Interface - 首字加 I 字母的 PascalCase。範例: IPlayerMove
9.  Variable - camelCase
10. Method - PascalCase
11. Method Parameters - camelCase
12. Event - PascelCase


### 程式碼範例

```csharp
namespace Mortal.Battle //Namespace, PascalCase
{
    public enum PlayerType  //Enum, PascalCase
    {
        Player = 1, //Enum value, PascalCase
        NPC = 2
    }

    public interface IPlayerInput   //Interface, I + PascalCase
    {
        Vector3 GetInput(); //Method, PascalCase
    }

    public class Player : IPlayerInput  //Class, PascalCase
    {
        public event OnRemove;  //Event, PascalCase

        private const float MAX_SPEED = 100f;   //Const, 全大寫，單字間用底線隔開

        // Private fields, underscore + camelCase
        private string _name;   
        private float _moveSpeed;

        // Public property, PascalCase
        public string Name => _name;
        public float MoveSpeed => _moveSpeed;

        public Vector3 GetInput()
        {
            Vector3 result = Vector3.zero;  // Variable, camelCase
            return result;
        }

        public void Move()
        {
            Vector3 input = GetInput();
            Vector3 move = input * _moveSpeed;
            // Do something...
        }

        public void SetName(string name)    //Method parameters, camelCase
        {
            _name = name;
        }
    }
}
```


## Region 區塊定義

用途 - 若檔案內的程式碼行數過多，可考慮使用 #region 區塊整理程式碼

- 下列為比較常使用到的區塊

1. #region Private fields - 私有變數或屬性
2. #region Public fields - 公開變數或屬性
3. #region Unity - 放置 Unity 生命週期呼叫的函式
4. #region Public methods - 公開方法
5. #region Helper - 私有方法
   
- 無法歸類在上述的區塊，可自行定義
