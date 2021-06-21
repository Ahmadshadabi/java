# java
Name:game Little

private void _Click(object sender, EventArgs e)
		{	if (GameStatus == GameStatus.Continue)		{
				Me me = (me)sender;

			if (me != null && me.Status != "Dead")
			{
					PlayBirdHitSound();
					Me.Status = "Dead";
				Me.Image.RotateFlip(RotateFlipType.Rotate270FlipNone);
					Me.Image = Properties.Resources.explosion_animation;
				}
				else
				{
					PlayGunSound();
				}
			}
		}
		
		private void PlayGameForm_Click(object sender, EventArgs e)
		{
			if (GameStatus == GameStatus.Continue)
			{
				PlayGunSound();
			}
		}		

		private void RemoveBird(BirdTimer BirdTimer)	{
			if (BirdTimer != null)
			{
				FlyingBirds.Remove(BirdTimer);

				Me.Stop();
				Meimer.me.Dispose();
				Me.Dispose();
			}
		}
 

