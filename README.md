# SHARING
用于临时的展示和交互

# 代码
以下是一个职高高一的小孩哥用kimi 做出来的和平精英Android手游自瞄外挂, 自称能实现把屏幕准星移动到游戏画面出现的对手身上.
使用方式为:直接导入到游戏根目录的JAVA文件夹就行了
以下是他提供的所有代码

'''
java
package com.tencent.tmgp.pubgmhd;

public class Main {
    public static void main(String[] args) {
        // 创建 FastHeadshotMaster 类的实例
        FastHeadshotMaster fastHeadshotMaster = new FastHeadshotMaster();

        // 启用快速爆头功能
        fastHeadshotMaster.setFastHeadshotEnabled(true);

        // 设置自动瞄准强度为 1.0
        fastHeadshotMaster.setAutoAimStrength(9.0);

        // 设置锁定视野范围为 120
        fastHeadshotMaster.setLockFOV(120);

        // 设置锁定延迟时间为 0.5 秒
        fastHeadshotMaster.setLockDelay(0.1);

        // 启用无声瞄准功能
        fastHeadshotMaster.setSilentAim(true);

        // 启用自动射击功能
        fastHeadshotMaster.setAutoFire(true);

        // 启用瞬间命中功能
        fastHeadshotMaster.setInstantHit(true);

        // 启用子弹穿透功能
        fastHeadshotMaster.setBulletPenetration(true);

        // 启用子弹制导功能
        fastHeadshotMaster.setBulletHoming(true);

        // 设置子弹追踪速度为 10.0
        fastHeadshotMaster.setBulletTrackSpeed(30.0);

        // 启用无后坐力功能
        fastHeadshotMaster.setNoRecoil(true);

        // 启用无扩散功能
        fastHeadshotMaster.setNoSpread(true);

        // 启用X光透视功能
        fastHeadshotMaster.setXRayVision(true);

        // 启用敌人发光功能
        fastHeadshotMaster.setEnemyGlow(true);

        // 设置AI优先级为 "High"
        fastHeadshotMaster.setAIPriority("High");

        // 设置AI扫描半径为 50.0
        fastHeadshotMaster.setAIScanRadius(90.0);

        // 设置AI反应时间为 0.2
        fastHeadshotMaster.setAIReactionTime(0.5);

        // 设置最大目标数为 5
        fastHeadshotMaster.setMaxTargets(5);

        // 删除激活键相关代码
        // fastHeadshotMaster.setActivationKey("F1");

        // 设置命中框放大倍数为 1.5
        fastHeadshotMaster.setHitboxEnlarge(1.5);

        // 启用网络优化功能
        fastHeadshotMaster.setNetworkOptimize(true);

        // 设置引擎版本为 "1.0.0"
        fastHeadshotMaster.setEngineVersion("1.0.0");

        // 设置日志级别为 2
        fastHeadshotMaster.setLogLevel(2);

        // 打印当前设置
        System.out.println("快速爆头功能是否启用: " + fastHeadshotMaster.fastHeadshotEnabled);
        System.out.println("自动瞄准强度: " + fastHeadshotMaster.autoAimStrength);
        System.out.println("锁定视野范围: " + fastHeadshotMaster.lockFOV);
        System.out.println("锁定延迟时间: " + fastHeadshotMaster.lockDelay);
        System.out.println("无声瞄准功能是否启用: " + fastHeadshotMaster.silentAim);
        System.out.println("自动射击功能是否启用: " + fastHeadshotMaster.autoFire);
        System.out.println("瞬间命中功能是否启用: " + fastHeadshotMaster.instantHit);
        System.out.println("子弹穿透功能是否启用: " + fastHeadshotMaster.bulletPenetration);
        System.out.println("子弹制导功能是否启用: " + fastHeadshotMaster.bulletHoming);
        System.out.println("子弹追踪速度: " + fastHeadshotMaster.bulletTrackSpeed);
        System.out.println("无后坐力功能是否启用: " + fastHeadshotMaster.noRecoil);
        System.out.println("无扩散功能是否启用: " + fastHeadshotMaster.noSpread);
        System.out.println("X光透视功能是否启用: " + fastHeadshotMaster.xRayVision);
        System.out.println("敌人发光功能是否启用: " + fastHeadshotMaster.enemyGlow);
        System.out.println("AI优先级: " + fastHeadshotMaster.aiPriority);
        System.out.println("AI扫描半径: " + fastHeadshotMaster.aiScanRadius);
        System.out.println("AI反应时间: " + fastHeadshotMaster.aiReactionTime);
        System.out.println("最大目标数: " + fastHeadshotMaster.maxTargets);
        System.out.println("命中框放大倍数: " + fastHeadshotMaster.hitboxEnlarge);
        System.out.println("网络优化功能是否启用: " + fastHeadshotMaster.networkOptimize);
        System.out.println("引擎版本: " + fastHeadshotMaster.engineVersion);
        System.out.println("日志级别: " + fastHeadshotMaster.logLevel);
    }
}
'''


'''
java
import javax.swing.*;
import java.awt.*;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;

public class Autoaim {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Autoaim");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 400);

        JPanel panel = new JPanel() {
            @Override
            protected void paintComponent(Graphics g) {
                super.paintComponent(g);
                g.setColor(Color.RED);
                g.fillOval(150, 150, 50, 50);
            }
        };

        panel.addMouseMotionListener(new MouseAdapter() {
            @Override
            public void mouseMoved(MouseEvent e) {
                int x = e.getX();
                int y = e.getY();
                int centerX = panel.getWidth() / 2;
                int centerY = panel.getHeight() / 2;
                double distance = Math.sqrt(Math.pow(x - centerX, 2) + Math.pow(y - centerY, 2));
                if (distance <= 75) {
                    System.out.println("Aimed at the target");
                    panel.setCursor(Cursor.getPredefinedCursor(Cursor.CROSSHAIR_CURSOR));
                } else {
                    panel.setCursor(Cursor.getPredefinedCursor(Cursor.DEFAULT_CURSOR));
                }
            }
        });

        frame.add(panel);
        frame.setVisible(true);
    }
}
'''
'''
java
class Player {
    private float x, y; // 玩家位置
    private float aimX, aimY; // 玩家瞄准的方向

    public Player(float x, float y) {
        this.x = x;
        this.y = y;
        this.aimX = x;
        this.aimY = y;
    }

    public void updateAim(float targetX, float targetY) {
        // 强制锁定目标位置
        aimX = targetX;
        aimY = targetY;

        // 边界检查，防止瞄准方向超出合理范围
        aimX = Math.max(0, Math.min(aimX, 100)); // 假设 X 轴的合理范围是 0 到 100
        aimY = Math.max(0, Math.min(aimY, 100)); // 假设 Y 轴的合理范围是 0 到 100
    }

    public float getAimX() {
        return aimX;
    }

    public float getAimY() {
        return aimY;
    }
}

class Target {
    private float x, y; // 目标位置
    private float velocityX, velocityY; // 目标速度

    public Target(float x, float y, float velocityX, float velocityY) {
        this.x = x;
        this.y = y;
        this.velocityX = velocityX;
        this.velocityY = velocityY;
    }

    public void move() {
        // 更新目标位置
        x += velocityX;
        y += velocityY;
    }

    public float getX() {
        return x;
    }

    public float getY() {
        return y;
    }

    public float getVelocityX() {
        return velocityX;
    }

    public float getVelocityY() {
        return velocityY;
    }
}

public class Main {
    public static void main(String[] args) {
        Player player = new Player(0, 0); // 玩家初始位置在 (0, 0)
        Target target = new Target(10, 10, 1, 1); // 目标初始位置在 (10, 10)，速度为 (1, 1)

        // 模拟玩家瞄准目标的过程
        for (int i = 0; i < 20; i++) {
            // 预测目标的未来位置
            float predictedX = target.getX() + target.getVelocityX() * (i + 1);
            float predictedY = target.getY() + target.getVelocityY() * (i + 1);

            // 更新玩家的瞄准方向为预测位置
            player.updateAim(predictedX, predictedY);
            System.out.println("Aim X: " + player.getAimX() + ", Aim Y: " + player.getAimY());

            // 更新目标位置
            target.move();
        }
    }
}

'''
'''
java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.util.ArrayList;

public class GamePanel extends JPanel implements ActionListener {
    private Timer timer;
    private Player player;
    private ArrayList<Target> targets;

    public GamePanel() {
        timer = new Timer(30, this); // 每30ms更新一次
        player = new Player(100, 500); // 玩家初始位置
        targets = new ArrayList<>();
        targets.add(new Target(300, 300, 2, 2)); // 添加一个目标，速度为 (2, 2)
        timer.start();
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        // 自动瞄准逻辑
        Target closestTarget = findClosestTarget(player, targets);
        if (closestTarget != null) {
            Vector2 aimPosition = predictTargetPosition(closestTarget, 1); // 预测1帧后的目标位置
            player.updateAim((int) aimPosition.x, (int) aimPosition.y);
        }
        repaint();
    }

    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        g.setColor(Color.BLUE);
        g.fillRect(player.getX(), player.getY(), 20, 20); // 绘制玩家
        g.setColor(Color.RED);
        g.fillRect(player.getAimX(), player.getAimY(), 5, 5); // 绘制瞄准位置
        g.setColor(Color.GREEN);
        for (Target target : targets) {
            g.fillRect(target.getX(), target.getY(), 20, 20); // 绘制目标
        }
    }

    public static void main(String[] args) {
        JFrame frame = new JFrame("Game Panel");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(800, 600);
        frame.add(new GamePanel());
        frame.setVisible(true);
    }

    private Target findClosestTarget(Player player, ArrayList<Target> targets) {
        double closestDistance = Double.MAX_VALUE;
        Target closestTarget = null;
        for (Target target : targets) {
            double distance = Math.sqrt(Math.pow(target.getX() - player.getX(), 2) + Math.pow(target.getY() - player.getY(), 2));
            if (distance < closestDistance) {
                closestDistance = distance;
                closestTarget = target;
            }
        }
        return closestTarget;
    }

    private Vector2 predictTargetPosition(Target target, int frames) {
        double predictedX = target.getX() + target.getVelocityX() * frames;
        double predictedY = target.getY() + target.getVelocityY() * frames;
        return new Vector2(predictedX, predictedY);
    }
}

class Vector2 {
    public double x, y;

    public Vector2(double x, double y) {
        this.x = x;
        this.y = y;
    }
}

class Player {
    private int x;
    private int y;
    private int aimX;
    private int aimY;

    public Player(int x, int y) {
        this.x = x;
        this.y = y;
        this.aimX = x;
        this.aimY = y;
    }

    public void updateAim(int aimX, int aimY) {
        this.aimX = aimX;
        this.aimY = aimY;
    }

    public int getX() {
        return x;
    }

    public int getY() {
        return y;
    }

    public int getAimX() {
        return aimX;
    }

    public int getAimY() {
        return aimY;
    }
}

class Target {
    private int x;
    private int y;
    private int velocityX;
    private int velocityY;

    public Target(int x, int y, int velocityX, int velocityY) {
        this.x = x;
        this.y = y;
        this.velocityX = velocityX;
        this.velocityY = velocityY;
    }

    public int getX() {
        return x;
    }

    public int getY() {
        return y;
    }

    public int getVelocityX() {
        return velocityX;
    }

    public int getVelocityY() {
        return velocityY;
    }
}
'''

