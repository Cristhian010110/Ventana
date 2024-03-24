# Ventana
using OpenTK.Mathematics;
using OpenTK.Windowing.Common;
using OpenTK.Windowing.Desktop;
using OpenTK.Graphics.OpenGL4; // Agrega esta línea


namespace TuProyecto
{
    public class Game : GameWindow
    {
        public Game() : base(GameWindowSettings.Default, new NativeWindowSettings()
        {
            Size = new Vector2i(800, 600),
            Title = "Mi Ventana OpenTK"
        })
        {
            // Cambia el color de fondo a un tono azul claro
            this.RenderFrame += OnRenderFrame;
        }

        private void OnRenderFrame(FrameEventArgs e)
        {
            GL.ClearColor(0.6f, 0.8f, 1.0f, 1.0f); // Establece el color de fondo
            GL.Clear(ClearBufferMask.ColorBufferBit | ClearBufferMask.DepthBufferBit);

            // Aquí puedes agregar la lógica de renderizado de tu juego

            SwapBuffers();
        }
    }
}
//PROGRAM.CS
using System;

namespace TuProyecto
{
    class Program
    {
        static void Main(string[] args)
        {
            using (var game = new Game())
            {
                game.Run();
            }
        }
    }
}
